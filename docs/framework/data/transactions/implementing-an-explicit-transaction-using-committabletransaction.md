---
title: "Implementando uma transação explícita usando CommittableTransaction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f045356fa2de6543a3b24490cb7964640a8d802c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a><span data-ttu-id="c2e01-102">Implementando uma transação explícita usando CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="c2e01-102">Implementing an Explicit Transaction using CommittableTransaction</span></span>
<span data-ttu-id="c2e01-103">O <xref:System.Transactions.CommittableTransaction> classe fornece um modo explícito para os aplicativos que usam uma transação, em vez de usar o <xref:System.Transactions.TransactionScope> classe implicitamente.</span><span class="sxs-lookup"><span data-stu-id="c2e01-103">The <xref:System.Transactions.CommittableTransaction> class provides an explicit way for applications to use a transaction, as opposed to using the <xref:System.Transactions.TransactionScope> class implicitly.</span></span> <span data-ttu-id="c2e01-104">É útil para aplicativos que deseja usar a mesma transação em várias chamadas de função ou várias chamadas de threads.</span><span class="sxs-lookup"><span data-stu-id="c2e01-104">It is useful for applications that want to use the same transaction across multiple function calls or multiple thread calls.</span></span> <span data-ttu-id="c2e01-105">Ao contrário do <xref:System.Transactions.TransactionScope> classe, o criador do aplicativo precisa chamar especificamente o <xref:System.Transactions.CommittableTransaction.Commit%2A> e <xref:System.Transactions.Transaction.Rollback%2A> métodos para confirmar ou anular a transação.</span><span class="sxs-lookup"><span data-stu-id="c2e01-105">Unlike the <xref:System.Transactions.TransactionScope> class, the application writer needs to specifically call the <xref:System.Transactions.CommittableTransaction.Commit%2A> and <xref:System.Transactions.Transaction.Rollback%2A> methods in order to commit or abort the transaction.</span></span>  
  
## <a name="overview-of-the-committabletransaction-class"></a><span data-ttu-id="c2e01-106">Visão geral da classe CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="c2e01-106">Overview of the CommittableTransaction class</span></span>  
 <span data-ttu-id="c2e01-107">O <xref:System.Transactions.CommittableTransaction> classe deriva de <xref:System.Transactions.Transaction> classe, fornecendo, portanto, toda a funcionalidade do último.</span><span class="sxs-lookup"><span data-stu-id="c2e01-107">The <xref:System.Transactions.CommittableTransaction> class derives from the <xref:System.Transactions.Transaction> class, therefore providing all the functionality of the latter.</span></span> <span data-ttu-id="c2e01-108">É especificamente útil a <xref:System.Transactions.Transaction.Rollback%2A> método o <xref:System.Transactions.Transaction> classe também pode ser usado para reverter uma <xref:System.Transactions.CommittableTransaction> objeto.</span><span class="sxs-lookup"><span data-stu-id="c2e01-108">Specifically useful is the <xref:System.Transactions.Transaction.Rollback%2A> method on the <xref:System.Transactions.Transaction> class that can also be used to rollback a <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="c2e01-109">O <xref:System.Transactions.Transaction> classe é semelhante de <xref:System.Transactions.CommittableTransaction> de classe, mas não oferece uma `Commit` método.</span><span class="sxs-lookup"><span data-stu-id="c2e01-109">The  <xref:System.Transactions.Transaction> class is similar to the <xref:System.Transactions.CommittableTransaction> class but does not offer a `Commit` method.</span></span> <span data-ttu-id="c2e01-110">Isso permite que você passe o objeto de transação (ou clones dele) para outros métodos (potencialmente em outros threads) enquanto ainda controla quando a transação é confirmada.</span><span class="sxs-lookup"><span data-stu-id="c2e01-110">This enables you to pass the transaction object (or clones of it) to other methods (potentially on other threads) while still controlling when the transaction is committed.</span></span> <span data-ttu-id="c2e01-111">O código de chamada é capaz de se inscrever e votar na transação, mas somente o criador do <xref:System.Transactions.CommittableTransaction> objeto tem a capacidade de confirmar a transação.</span><span class="sxs-lookup"><span data-stu-id="c2e01-111">The called code is able to enlist and vote on the transaction, but only the creator of the <xref:System.Transactions.CommittableTransaction> object has the ability to commit the transaction.</span></span>  
  
 <span data-ttu-id="c2e01-112">Observe o seguinte ao trabalhar com o <xref:System.Transactions.CommittableTransaction> classe,</span><span class="sxs-lookup"><span data-stu-id="c2e01-112">You should note the followings when working with the <xref:System.Transactions.CommittableTransaction> class,</span></span>  
  
-   <span data-ttu-id="c2e01-113">Criando um <xref:System.Transactions.CommittableTransaction> transação não define a transação de ambiente.</span><span class="sxs-lookup"><span data-stu-id="c2e01-113">Creating a <xref:System.Transactions.CommittableTransaction> transaction does not set the ambient transaction.</span></span> <span data-ttu-id="c2e01-114">Você precisa definir especificamente e redefinir a transação ambiente, para garantir que os gerenciadores de recursos operam sob o contexto de transação direita quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="c2e01-114">You need to specifically set and reset the ambient transaction, to ensure that resource managers operate under the right transaction context when appropriate.</span></span> <span data-ttu-id="c2e01-115">A maneira de definir a transação de ambiente atual está definindo estático <xref:System.Transactions.Transaction.Current%2A> propriedade global <xref:System.Transactions.Transaction> objeto.</span><span class="sxs-lookup"><span data-stu-id="c2e01-115">The way to set the current ambient transaction is by setting the static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object.</span></span>  
  
-   <span data-ttu-id="c2e01-116">Um <xref:System.Transactions.CommittableTransaction> objeto não pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="c2e01-116">A <xref:System.Transactions.CommittableTransaction> object cannot be reused.</span></span> <span data-ttu-id="c2e01-117">Uma vez um <xref:System.Transactions.CommittableTransaction> objeto foi confirmado ou revertido, ele não pode ser usado novamente em uma transação.</span><span class="sxs-lookup"><span data-stu-id="c2e01-117">Once a <xref:System.Transactions.CommittableTransaction> object has been committed or rolled back, it cannot be used again in a transaction.</span></span> <span data-ttu-id="c2e01-118">Ou seja, ele não pode ser definido como o contexto de transação de ambiente atual.</span><span class="sxs-lookup"><span data-stu-id="c2e01-118">That is, it cannot be set as the current ambient transaction context.</span></span>  
  
## <a name="creating-a-committabletransaction"></a><span data-ttu-id="c2e01-119">Criando um CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="c2e01-119">Creating a CommittableTransaction</span></span>  
 <span data-ttu-id="c2e01-120">O exemplo a seguir cria um novo <xref:System.Transactions.CommittableTransaction> e confirma a ele.</span><span class="sxs-lookup"><span data-stu-id="c2e01-120">The following sample creates a new <xref:System.Transactions.CommittableTransaction> and commits it.</span></span>  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 <span data-ttu-id="c2e01-121">Criando uma instância de <xref:System.Transactions.CommittableTransaction> não define automaticamente o contexto de transação de ambiente.</span><span class="sxs-lookup"><span data-stu-id="c2e01-121">Creating an instance of <xref:System.Transactions.CommittableTransaction> does not automatically set the ambient transaction context.</span></span> <span data-ttu-id="c2e01-122">Portanto, qualquer operação em um Gerenciador de recursos não é parte da transação.</span><span class="sxs-lookup"><span data-stu-id="c2e01-122">Therefore, any operation on a resource manager is not part of that transaction.</span></span> <span data-ttu-id="c2e01-123">Estático <xref:System.Transactions.Transaction.Current%2A> propriedade global <xref:System.Transactions.Transaction> objeto é usado para definir ou recuperar a transação de ambiente e o aplicativo deve defini-lo para garantir que os gerenciadores de recursos podem participar da transação manualmente.</span><span class="sxs-lookup"><span data-stu-id="c2e01-123">The static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object is used to set or retrieve the ambient transaction and the application must manually set it to ensure that resource managers can participate in the transaction.</span></span> <span data-ttu-id="c2e01-124">Também é uma boa prática para salvar a transação ambiente antiga e restaurá-lo quando terminar de usar o <xref:System.Transactions.CommittableTransaction> objeto.</span><span class="sxs-lookup"><span data-stu-id="c2e01-124">It is also a good practice to save the old ambient transaction and restore it when you finish using the <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="c2e01-125">Para confirmar a transação, você precisa chamar explicitamente o <xref:System.Transactions.CommittableTransaction.Commit%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c2e01-125">To commit the transaction, you need to explicitly call the <xref:System.Transactions.CommittableTransaction.Commit%2A> method.</span></span> <span data-ttu-id="c2e01-126">Para reverter uma transação, você deve chamar o <xref:System.Transactions.Transaction.Rollback%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c2e01-126">For rolling back a transaction, you should call the <xref:System.Transactions.Transaction.Rollback%2A> method.</span></span> <span data-ttu-id="c2e01-127">É importante observar que até um <xref:System.Transactions.CommittableTransaction> foi confirmada ou revertida, todos os recursos envolvidos nessa transação ainda estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c2e01-127">It is important to note that until a <xref:System.Transactions.CommittableTransaction> has been committed or rolled back, all the resources involved in that transaction are still locked.</span></span>  
  
 <span data-ttu-id="c2e01-128">Um <xref:System.Transactions.CommittableTransaction> objeto pode ser usado em chamadas de função e threads.</span><span class="sxs-lookup"><span data-stu-id="c2e01-128">A <xref:System.Transactions.CommittableTransaction> object can be used across function calls and threads.</span></span> <span data-ttu-id="c2e01-129">No entanto, é o desenvolvedor de aplicativo para manipular exceções e chamar especificamente o <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> método em caso de falhas.</span><span class="sxs-lookup"><span data-stu-id="c2e01-129">However, it is up to the application developer to handle exceptions and specifically call the <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> method in case of failures.</span></span>  
  
## <a name="asynchronous-commit"></a><span data-ttu-id="c2e01-130">Confirmação assíncrona</span><span class="sxs-lookup"><span data-stu-id="c2e01-130">Asynchronous Commit</span></span>  
 <span data-ttu-id="c2e01-131">O <xref:System.Transactions.CommittableTransaction> classe também fornece um mecanismo para confirmar uma transação de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="c2e01-131">The <xref:System.Transactions.CommittableTransaction> class also provides a mechanism for committing a transaction asynchronously.</span></span> <span data-ttu-id="c2e01-132">Uma confirmação de transação pode levar algum tempo, como ele pode envolver vários acesso de banco de dados e possível latência de rede.</span><span class="sxs-lookup"><span data-stu-id="c2e01-132">A transaction commit can take substantial time, as it might involve multiple database access and possible network latency.</span></span> <span data-ttu-id="c2e01-133">Quando você deseja evitar deadlocks em aplicativos de alta taxa de transferência, use confirmação assíncrona para concluir o trabalho transacional assim que possível e executar a operação de confirmação como uma tarefa em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c2e01-133">When you want to avoid deadlocks in high throughput applications, you can use asynchronous commit to finish the transactional work as soon as possible, and run the commit operation as a background task.</span></span> <span data-ttu-id="c2e01-134">O <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> e <xref:System.Transactions.CommittableTransaction.EndCommit%2A> métodos de <xref:System.Transactions.CommittableTransaction> classe permitem que você faça isso.</span><span class="sxs-lookup"><span data-stu-id="c2e01-134">The <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> and <xref:System.Transactions.CommittableTransaction.EndCommit%2A> methods of the <xref:System.Transactions.CommittableTransaction> class allow you to do so.</span></span>  
  
 <span data-ttu-id="c2e01-135">Você pode chamar <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> para expedir a demora de confirmação a um thread do pool de threads.</span><span class="sxs-lookup"><span data-stu-id="c2e01-135">You can call <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> to dispatch the commit holdup to a thread from the thread pool.</span></span> <span data-ttu-id="c2e01-136">Você também pode chamar <xref:System.Transactions.CommittableTransaction.EndCommit%2A> para determinar se a transação, na verdade, foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="c2e01-136">You can also call <xref:System.Transactions.CommittableTransaction.EndCommit%2A> to determine if the transaction has actually been committed.</span></span> <span data-ttu-id="c2e01-137">Se a transação não foi confirmada por algum motivo, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> gera uma exceção de transação.</span><span class="sxs-lookup"><span data-stu-id="c2e01-137">If the transaction failed to commit for whatever reason, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> raises a transaction exception.</span></span> <span data-ttu-id="c2e01-138">Se a transação é ainda não foram confirmada no momento <xref:System.Transactions.CommittableTransaction.EndCommit%2A> é chamado, o chamador é bloqueado até que a transação é confirmada ou anulada.</span><span class="sxs-lookup"><span data-stu-id="c2e01-138">If the transaction is not yet committed by the time <xref:System.Transactions.CommittableTransaction.EndCommit%2A> is called, the caller is blocked until the transaction is committed or aborted.</span></span>  
  
 <span data-ttu-id="c2e01-139">É a maneira mais fácil de fazer uma confirmação assíncrona, fornecendo um método de retorno de chamada a ser chamada quando a confirmação for concluída.</span><span class="sxs-lookup"><span data-stu-id="c2e01-139">The easiest way to do an asynchronous commit is by providing a callback method, to be called when committing is finished.</span></span> <span data-ttu-id="c2e01-140">No entanto, você deve chamar o <xref:System.Transactions.CommittableTransaction.EndCommit%2A> método no original <xref:System.Transactions.CommittableTransaction> objeto usado para invocar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c2e01-140">However, you must call the <xref:System.Transactions.CommittableTransaction.EndCommit%2A> method on the original <xref:System.Transactions.CommittableTransaction> object used to invoke the call.</span></span> <span data-ttu-id="c2e01-141">Para obter esse objeto, você pode baixá-los a *IAsyncResult* parâmetro do método de retorno de chamada, pois o <xref:System.Transactions.CommittableTransaction> classe implementa <xref:System.IAsyncResult> classe.</span><span class="sxs-lookup"><span data-stu-id="c2e01-141">To obtain that object, you can downcast the *IAsyncResult* parameter of the callback method, since the <xref:System.Transactions.CommittableTransaction> class implements <xref:System.IAsyncResult> class.</span></span>  
  
 <span data-ttu-id="c2e01-142">O exemplo a seguir mostra como uma confirmação assíncrona pode ser feita.</span><span class="sxs-lookup"><span data-stu-id="c2e01-142">The following example shows how an asynchronous commit can be done.</span></span>  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction   
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;     
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2e01-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c2e01-143">See Also</span></span>  
 [<span data-ttu-id="c2e01-144">Implementando uma transação implícita, usando o escopo da transação</span><span class="sxs-lookup"><span data-stu-id="c2e01-144">Implementing an Implicit Transaction using Transaction Scope</span></span>](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
 <span data-ttu-id="c2e01-145">[Transaction Processing](../../../../docs/framework/data/transactions/index.md) (Processamento de transações)</span><span class="sxs-lookup"><span data-stu-id="c2e01-145">[Transaction Processing](../../../../docs/framework/data/transactions/index.md)</span></span>
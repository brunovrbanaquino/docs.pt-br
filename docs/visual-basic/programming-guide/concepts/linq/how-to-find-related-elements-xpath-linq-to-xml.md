---
title: "Como: elementos inter-relacionados de alterações (XPath-LINQ para XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b0ef058-d704-48a5-98cd-33f00d088af9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6153db1e77b957d35160d1de75f18e163817ba6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-visual-basic"></a>Como: elementos inter-relacionados de alterações (XPath-LINQ para XML) (Visual Basic)
Este tópico mostra como obter um elemento que seleciona em um atributo que é chamada pelo valor de outro elemento.  
  
 A expressão XPath é:  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a>Exemplo  
 Este exemplo localiza o 12o elemento de `Order` , e localiza no cliente para essa ordem.  
  
 Observe a indexação em uma lista dentro. A rede é “" com base zero. A indexação em uma coleção de nós em um predicado XPath “é um” com base. Este exemplo reflete essa diferença.  
  
 Este exemplo usa o seguinte documento XML: [Arquivo XML de exemplo: clientes e pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim co As XDocument = XDocument.Load("CustomersOrders.xml")  
  
' LINQ to XML query  
Dim customer1 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        ToList()(11).<CustomerID>(0).Value _  
    Select el).First()  
  
' An alternate way to write the query that avoids creation  
' of a System.Collections.Generic.List:  
Dim customer2 As XElement = ( _  
    From el In co...<Customer> _  
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _  
        Skip(11).First().<CustomerID>(0).Value _  
    Select el).First()  
  
' XPath expression  
Dim customer3 As XElement = co.XPathSelectElement _  
    (".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]")  
  
If customer1 Is customer2 And customer1 Is customer3 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(customer1)  
```  
  
 Este exemplo gera a seguinte saída:  
  
```  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
  
## <a name="see-also"></a>Consulte também  
 [LINQ to XML para XPath usuários (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

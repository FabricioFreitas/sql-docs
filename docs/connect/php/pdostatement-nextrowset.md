---
title: "PDOStatement::nextRowset"
description: "API reference for the PDOStatement::nextRowset function in the Microsoft PDO_SQLSRV Driver for PHP for SQL Server."
ms.custom: ""
ms.date: "08/10/2020"
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ""
ms.technology: connectivity
ms.topic: reference
ms.assetid: 048a6d8f-7fc4-449e-8161-19268c68f41d
author: David-Engel
ms.author: v-davidengel
---
# PDOStatement::nextRowset
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Moves the cursor to the next result set.  
  
## Syntax  
  
```  
  
bool PDOStatement::nextRowset();  
```  
  
## Return Value  
true on success, false otherwise.  
  
## Remarks  
Support for PDO was added in version 2.0 of the [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## Example  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   $query1 = "select * from Person.Address where City = 'Bothell';";  
   $query2 = "select * from Person.ContactType;";  
  
   $stmt = $conn->query( $query1 . $query2 );  
  
   $rowset1 = $stmt->fetchAll();  
   $stmt->nextRowset();  
   $rowset2 = $stmt->fetchAll();  
   var_dump( $rowset1 );  
   var_dump( $rowset2 );  
?>  
```  
  
## See Also  
[PDOStatement Class](../../connect/php/pdostatement-class.md)

[PDO](https://php.net/manual/book.pdo.php)  
  

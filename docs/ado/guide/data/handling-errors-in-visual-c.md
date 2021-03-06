---
description: "Handling Errors in Visual C++"
title: "Handling Errors in Visual C++ | Microsoft Docs"
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.topic: conceptual
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "errors [ADO], Visual C++"
  - "Visual C++ error handling [ADO]"
ms.assetid: b7576f07-020a-45f7-9e79-b5756f33f7ab
author: rothja
ms.author: jroth
---
# Handling Errors in Visual C++
In COM, most operations return an HRESULT return code that indicates whether a function completed successfully. The #import directive generates wrapper code around each "raw" method or property and checks the returned HRESULT. If the HRESULT indicates failure, the wrapper code throws a COM error by calling _com_issue_errorex() with the HRESULT return code as an argument. COM error objects can be caught in a **try-catch** block. (For efficiency's sake, catch a reference to a _com_error object.)  
  
 Remember, these are ADO errors: they result from the ADO operation failing. Errors returned by the underlying provider appear as **Error** objects in the **Connection** object's **Errors** collection.  
  
 The #import directive only creates error-handling routines for methods and properties declared in the ADO .dll. However, you can take advantage of this same error-handling mechanism by writing your own error-checking macro or inline function. See the topic Visual C++® Extensions for examples.

---
title: "IDebugComPlusSymbolProvider::LoadSymbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: 
  - "vs-ide-sdk"
ms.topic: "conceptual"
helpviewer_keywords: 
  - "LoadSymbols"
  - "IDebugComPlusSymbolProvider::LoadSymbols"
ms.assetid: 3499680d-0b9a-4f20-8432-c89a41b29b87
author: "gregvanl"
ms.author: "gregvanl"
manager: douge
ms.workload: 
  - "vssdk"
---
# IDebugComPlusSymbolProvider::LoadSymbols
Loads the specified debug symbols in memory.  
  
## Syntax  
  
```cpp  
HRESULT LoadSymbols(  
   ULONG32   ulAppDomainID,  
   GUID      guidModule,  
   ULONGLONG baseAddress,  
   IUnknown* pUnkMetadataImport,  
   BSTR      bstrModuleName,  
   BSTR      bstrSymSearchPath  
);  
```  
  
```csharp  
int LoadSymbols(  
   uint   ulAppDomainID,  
   Guid   guidModule,  
   ulong  baseAddress,  
   object pUnkMetadataImport,  
   string bstrModuleName,  
   string bstrSymSearchPath  
);  
```  
  
#### Parameters  
 `ulAppDomainID`  
 [in] Identifier of the application domain.  
  
 `guidModule`  
 [in] Unique identifier of the mondule.  
  
 `baseAddress`  
 [in] Base memory address.  
  
 `pUnkMetadataImport`  
 [in] Object that contains the symbol metadata.  
  
 `bstrModuleName`  
 [in] Name of the module.  
  
 `bstrSymSearchPath`  
 [in] Path to search for the symbol file.  
  
## Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## Example  
 The following example shows how to implement this method for a **CDebugSymbolProvider** object that exposes the [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) interface.  
  
```cpp  
HRESULT CDebugSymbolProvider::LoadSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    ULONGLONG baseOffset,  
    IUnknown* _pMetadata,  
    BSTR bstrModule,  
    BSTR bstrSearchPath)  
{  
    return LoadSymbolsWithCorModule(ulAppDomainID, guidModule, baseOffset, _pMetadata, NULL, bstrModule, bstrSearchPath);  
}  
```  
  
## See Also  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
---
title: IDebugClassField | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugClassField
helpviewer_keywords:
- IDebugClassField interface
ms.assetid: 49358cbc-8973-4862-9dcc-79b1248e6712
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f549d72a3c6af9e6e7393ace4f30d06558d9af80
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695184"
---
# <a name="idebugclassfield"></a>IDebugClassField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugClassField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugclassfield).  
  
Bu arabirim türünde bir sınıfı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugClassField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Sembol sağlayıcısı bu arabirimi uygulayan aynı nesne üzerinde uygulayan [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) arabirimi. Bu sınıf türünü temsil eden bir özelleştirmesi arabirimidir.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir sayıda arabirimine sahip dahil bu arabirimi döndüren yöntemler [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), ve [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md). Ayrıca kullanabileceğiniz [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) bu arabirimden edinme [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) , arabirim [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) yöntemi bayrağı döndürür `FIELD_TYPE_CLASS`.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemlere ek olarak [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) ve [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) aşağıdaki arabirimleri, bu arabirimi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumBaseClasses](../../../extensibility/debugger/reference/idebugclassfield-enumbaseclasses.md)|Bu sınıfın temel sınıfları için bir numaralandırıcı oluşturur.|  
|[DoesInterfaceExist](../../../extensibility/debugger/reference/idebugclassfield-doesinterfaceexist.md)|Belirli bir arabirim sınıfta tanımlı olup olmadığını belirler.|  
|[EnumNestedClasses](../../../extensibility/debugger/reference/idebugclassfield-enumnestedclasses.md)|Bu sınıfın iç içe geçmiş sınıflar için bir numaralandırıcı oluşturur.|  
|[GetEnclosingClass](../../../extensibility/debugger/reference/idebugclassfield-getenclosingclass.md)|Bu sınıfın kapsayan sınıf alır.|  
|[EnumInterfacesImplemented](../../../extensibility/debugger/reference/idebugclassfield-enuminterfacesimplemented.md)|Bu sınıf tarafından uygulanan arabirimler için bir numaralandırıcı oluşturur.|  
|[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)|Bu sınıfın oluşturucuları için bir numaralandırıcı oluşturur.|  
|[GetDefaultIndexer](../../../extensibility/debugger/reference/idebugclassfield-getdefaultindexer.md)|Varsayılan oluşturucunun adını alır.|  
|[EnumNestedEnums](../../../extensibility/debugger/reference/idebugclassfield-enumnestedenums.md)|Bu sınıfın iç içe geçmiş numaralandırıcılar için bir numaralandırıcı oluşturur.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol sağlayıcısı arabirimleri](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)


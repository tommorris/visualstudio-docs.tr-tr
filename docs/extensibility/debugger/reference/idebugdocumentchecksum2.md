---
title: IDebugDocumentChecksum2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugDocumentChecksum2 interface
ms.assetid: 6d22fa94-21aa-46cb-b5b5-32a6399ebb20
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 50fbee2dbdb30873c97f1ca465d99161add90a19
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentchecksum2"></a>IDebugDocumentChecksum2
Hata ayıklama belge için bir sağlama toplamı temsil eder ve sağlama toplamı bileşenler arasında geçirme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugDocumentChecksum2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bu arabirim sunan herhangi bir bileşenin uygulanabilir [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) arabirimi. Ancak, katıştırılmış bir simge dosyası (*.pdb) sağlama toplamı IDE geçirilen ve bir kaynağı bulma işleminde kullanılan hata ayıklama altyapılarının temelde uygulandığı.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugDocumentChecksum2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetChecksumAndAlgorithmId](../../../extensibility/debugger/reference/idebugdocumentchecksum2-getchecksumandalgorithmid.md)|Kullanmak için bayt sayısını verilen belge sağlama toplamı ve algoritma tanımlayıcısını alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll
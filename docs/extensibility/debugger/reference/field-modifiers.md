---
title: FIELD_MODIFIERS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FIELD_MODIFIERS
helpviewer_keywords: FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f25d87193daf651f831b6b9ce584e6fa39a29991
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
Alan türü için değiştiriciler belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_FIELD_MODIFIERS {   
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
typedef DWORD FIELD_MODIFIERS;  
```  
  
```csharp  
public enum enum_FIELD_MODIFIERS {  
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 FIELD_MOD_ACCESS_TYPE  
 Alan erişilemez gösterir.  
  
 FIELD_MOD_ACCESS_PUBLIC  
 Alan genel erişimi olduğunu gösterir.  
  
 FIELD_MOD_ACCESS_PROTECTED  
 Alan Korumalı Erişim olduğunu gösterir.  
  
 FIELD_MOD_ACCESS_PRIVATE  
 Alan özel erişimi olduğunu gösterir.  
  
 FIELD_MOD_NOMODIFIERS  
 Alan Değiştirici yok sahip olduğunu gösterir.  
  
 FIELD_MOD_STATIC  
 Alan statik olduğunu gösterir.  
  
 FIELD_MOD_CONSTANT  
 Alan bir sabit olduğunu gösterir.  
  
 FIELD_MOD_TRANSIENT  
 Alan geçici olduğunu gösterir.  
  
 FIELD_MOD_VOLATILE  
 Alan volatile olduğunu gösterir.  
  
 FIELD_MOD_ABSTRACT  
 Alan soyut olduğunu gösterir.  
  
 FIELD_MOD_NATIVE  
 Alan yerel olduğunu gösterir.  
  
 FIELD_MOD_SYNCHRONIZED  
 Alan eşitlenir gösterir.  
  
 FIELD_MOD_VIRTUAL  
 Alan sanal olduğunu gösterir.  
  
 FIELD_MOD_INTERFACE  
 Alan bir arabirim olduğunu gösterir.  
  
 FIELD_MOD_FINAL  
 Alan son olduğunu gösterir.  
  
 FIELD_MOD_SENTINEL  
 Alan bir sentinel olduğunu gösterir.  
  
 FIELD_MOD_INNERCLASS  
 Alan bir iç sınıf olduğunu gösterir.  
  
 FIELD_TYPE_OPTIONAL  
 Alan isteğe bağlı olduğunu gösterir.  
  
 FIELD_MOD_BYREF  
 Alan başvurusu bağımsız değişkeni olduğunu gösterir. Bu, özellikle yöntem bağımsız değişkenleri için olur.  
  
 FIELD_MOD_HIDDEN  
 Alan gizli veya gereken başka bir bağlamda sunulan olduğunu gösterir; Örneğin, [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] statik Yereller.  
  
 FIELD_MOD_MARSHALASOBJECT  
 Alanı olan bir nesne temsil ettiğini belirten bir `IUnknown` arabirimi.  
  
 FIELD_MOD_SPECIAL_NAME  
 Alan özel bir ad, örneğin, sahip olduğunu gösterir `.ctor` Oluşturucu için ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] yalnızca).  
  
 FIELD_MOD_HIDEBYSIG  
 Alan olduğunu gösterir `Overloads` uygulanan anahtar sözcüğü ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] yalnızca).  
  
 FIELD_MOD_WRITEONLY  
 Alan yalnızca yazma olduğunu gösterir. Bu değer dahil edilmeyen `FIELD_MOD_ALL`, yalnızca bu tür yalnızca yazma alanlarının İşlev değerlendirmesi için kullanılır. Bir kullanıcı için açıkça başvurmalısınız `FIELD_MOD_WRITEONLY` alanları.  
  
 FIELD_MOD_ACCESS_MASK  
 Alan erişimi için bir maskesi gösterir.  
  
 FIELD_MOD_MASK  
 Alan değiştiricilerini maskesini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `dwModifiers` üyesi [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) yapısı.  
  
 Bu değerleri de geçirilen [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md) belirli alanlar için filtre uygulamak için yöntem.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)
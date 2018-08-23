---
title: Tür Koleksiyonu Düzenleyicisi iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 34b8129b5a0b1fe27a7e4e6c178ddace638e5ffc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680888"
---
# <a name="type-collection-editor-dialog-box"></a>Tür Koleksiyonu Düzenleyicisi İletişim Kutusu
**Editor Typu Kolekce** iletişim kutusu için bilinen türleri eklemek için kullanılan **Gönder** ve **alma** etkinlikler. Bu iletişim için genel tür bağımsız değişkeni eklemek için de kullanılır **InvokeMethod** etkinlik. İçin kullanıldığında **Gönder** ve **alma** bilinen türleri eklenecek etkinlikleri **Editor Typu Kolekce** iletişim kutusu türü eklemeleri benzersiz olmasını gerektirir. Yinelenen tür eklenir ve değişiklik tıklayarak kararlıdır **Tamam**, bir hata iletisi döndürülür. İçin kullanıldığında **InvokeMethod** genel tür bağımsız değişkenleri, eklemek için etkinlik **Editor Typu Kolekce** yinelenen türlerinin eklenmesi iletişim kutusu sağlar.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../includes/crabout-md.md)] bilinen türler, bkz: [veri sözleşme bilinen türleri](http://msdn.microsoft.com/library/1a0baea1-27b7-470d-9136-5bbad86c4337).  
  
 Aşağıdaki tabloda kullanıcı arabirimi (UI) öğelerini açıklar **türü koleksiyonu** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**Tür Listesi**|Eklenen veya kaldırılan türlerinin listesi.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Editor Typu Kolekce yukarı getirmek için  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Editor Typu Kolekce yedeklemek için Gönder getirin ve etkinlikleri almak için  
  
1.  Seçin **Gönder** veya **alma** Tasarım görünümünde etkinlik.  
  
2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.  
  
3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **KnownTypes** özelliği.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>InvokeMethod etkinliği için tür Koleksiyonu Düzenleyicisi'kurmak getirmek için  
  
1.  Seçin **InvokeMethod** Tasarım görünümünde etkinlik.  
  
2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.  
  
3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **GenericTypeArguments** özelliği.
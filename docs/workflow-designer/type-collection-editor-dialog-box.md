---
title: "Türü koleksiyon Düzenleyicisi iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: bdc27b59640d92507956030fc34c767e321a81fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="type-collection-editor-dialog-box"></a>Türü koleksiyon Düzenleyicisi iletişim kutusu
**Türü Koleksiyonu Düzenleyicisi** iletişim kutusu için bilinen türleri eklemek için kullanılan **Gönder** ve **alma** etkinlikler. Bu iletişim kutusunu da genel tür bağımsız değişkenleri eklemek için kullanılan **InvokeMethod** etkinlik. İçin kullanıldığında **Gönder** ve **alma** bilinen türleri eklenecek etkinlikleri **türü Koleksiyonu Düzenleyicisi** iletişim kutusu türü eklemeleri benzersiz olmasını gerektirir. Yinelenen türü eklenir ve değişiklik tıklayarak kararlıdır **Tamam**, bir hata iletisi döndürülür. İçin kullanıldığında **InvokeMethod** genel tür bağımsız değişkenleri eklemek için etkinlik **türü Koleksiyonu Düzenleyicisi** iletişim kutusu yinelenen türleri eklenmesini sağlar.  
  
> [!NOTE]
>  [! DAHİL[crabout](/dotnet/framework/wcf/feature-details/data-contract-known-types).  
  
 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **türü koleksiyonu** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**Tür listesi**|Eklenen veya kaldırılan türlerinin listesi.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Yedekleme türü koleksiyon Düzenleyicisi'ni getirmek için  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Yedekleme türü koleksiyon Düzenleyicisi'ni Gönder getirip etkinlikleri alma  
  
1.  Seçin **Gönder** veya **alma** Tasarım görünümünde etkinlik.  
  
2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.  
  
3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **KnownTypes** özelliği.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Yukarı türü Koleksiyonu Düzenleyicisi InvokeMethod etkinliğinin getirmek için  
  
1.  Seçin **InvokeMethod** Tasarım görünümünde etkinlik.  
  
2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.  
  
3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **GenericTypeArguments** özelliği.
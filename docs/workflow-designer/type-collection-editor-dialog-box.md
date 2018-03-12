---
title: "Türü koleksiyon Düzenleyicisi iletişim kutusu | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f873ef2f2f30e307c7f9ec16a612eb76d09633c9
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="type-collection-editor-dialog-box"></a>Türü koleksiyon Düzenleyicisi iletişim kutusu

**Türü Koleksiyonu Düzenleyicisi** iletişim kutusu için bilinen türleri eklemek için kullanılan **Gönder** ve **alma** etkinlikler. Bu iletişim kutusunu da genel tür bağımsız değişkenleri eklemek için kullanılan **InvokeMethod** etkinlik. İçin kullanıldığında **Gönder** ve **alma** bilinen türleri eklenecek etkinlikleri **türü Koleksiyonu Düzenleyicisi** iletişim kutusu türü eklemeleri benzersiz olmasını gerektirir. Yinelenen türü eklenir ve değişiklik tıklayarak kararlıdır **Tamam**, bir hata iletisi döndürülür. İçin kullanıldığında **InvokeMethod** genel tür bağımsız değişkenleri eklemek için etkinlik **türü Koleksiyonu Düzenleyicisi** iletişim kutusu yinelenen türleri eklenmesini sağlar.

Daha fazla bilgi için bkz: [veri sözleşmesi bilinen türler](/dotnet/framework/wcf/feature-details/data-contract-known-types).

Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **türü koleksiyonu** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**Tür Listesi**|Eklenen veya kaldırılan türlerinin listesi.|

## <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Yedekleme türü koleksiyon Düzenleyicisi'ni Gönder getirip etkinlikleri alma

1.  Seçin **Gönder** veya **alma** Tasarım görünümünde etkinlik.

2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.

3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **KnownTypes** özelliği.

## <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Yukarı türü Koleksiyonu Düzenleyicisi InvokeMethod etkinliğinin getirmek için

1.  Seçin **InvokeMethod** Tasarım görünümünde etkinlik.

2.  Tuşuna **F4** ortaya çıkarmak için **özellikleri** penceresi.

3.  İçinde **özellikleri** penceresinde, yanındaki üç nokta düğmesini tıklatın **GenericTypeArguments** özelliği.
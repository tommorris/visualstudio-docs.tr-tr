---
title: İş Akışı Tasarımcısı - türü koleksiyon Düzenleyicisi iletişim kutusu
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09bb5c7789be78a39a8d33a556ce66385db4a1d8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
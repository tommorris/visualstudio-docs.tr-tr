---
title: "Nasıl yapılır: Word belgelerine XMLNodes denetimleri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c6410f3bdb1f74ce935715260572cbd17d4670c2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-xmlnodes-controls-to-word-documents"></a>Nasıl Yapılır: Word Belgelerine XMLNodes Denetimleri Ekleme
  **Önemli** Microsoft Word ile ilgili bu konudaki ayarlanan bilgileri avantajı ve kişiler ve kimlerin bulunur Amerika Birleşik Devletleri ve alt bölgeleri dışında veya kullanan kuruluşlar için özel olarak sunulan ya da geliştirme çalışan programlar Ocak Microsoft uygulaması belirli işlevlerin ne zaman kaldırıldı 2010'dan önce Microsoft tarafından lisanslanan Microsoft Word ürünleri için özel XML Microsoft Word içinden ilgili. Bu bilgiler Microsoft Word ile ilgili okumak veya kişiler veya Amerika Birleşik Devletleri ya da kimin kullanarak veya Microsoft tarafından 10 Ocak 2010 sonra lisanslı Microsoft Word ürünleri hakkında çalışan programlar geliştirme kendi bölgeleri kuruluşlar tarafından kullanılan ; Bu ürün bu tarihten önce lisanslı veya satın alınan ve Amerika Birleşik Devletleri dışında kullanmak için lisanslı ürünleri ile aynı davranır değil.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Microsoft Office Word belgesine tekrarlanan bir XML şema öğesi eşlediğinizde, Visual Studio otomatik olarak ekler bir <xref:Microsoft.Office.Tools.Word.XMLNodes> belgenize denetimi.  
  
 Yinelenmeyen XML Şeması öğelerini eşleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNodes> Denetim kullanılabilir değil **araç** veya **veri kaynakları** pencere de can programlı olarak oluşturulabilir.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-an-xmlnodes-control-to-a-document"></a>XMLNodes denetimi bir belgeye eklemek için  
  
1.  Visual Studio tasarımcısında Şerit üzerindeki belgede tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
2.  İçinde **XML** grubunda **şema**.  
  
     **Şablonları ve eklentiler** iletişim kutusu açılır.  
  
3.  Tıklatın **XML Şeması** sekmesi.  
  
4.  Tıklatın **şeması eklemek**.  
  
     **Şema Ekle** iletişim kutusu açılır.  
  
5.  Yinelenen şema öğeleri ve tıklatın içeren bir XML şeması seçin **açık**.  
  
     **Şema ayarları** iletişim kutusu görüntülenir.  
  
6.  Bir ad atayın veya tıklatın **Tamam** bir diğer ad olmadan şema eklemek için.  
  
     Şema eklenen **Şema Ekle** iletişim kutusu.  
  
7.  İçinde **Şema Ekle** iletişim kutusu, tıklatın **Tamam**.  
  
     **XML yapısı** görev bölmesi açılır.  
  
8.  Yinelenen şema öğesi tıklayın **XML yapısı** belgeye eklemek için görev bölmesini.  
  
     Bir <xref:Microsoft.Office.Tools.Word.XMLNodes> denetimi oluşturulup projeye eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XMLNodes denetimi](../vsto/xmlnodes-control.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  
---
title: "SharePoint için site sütunları, içerik türleri ve listeler oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.ListDesigner.ContentTypeSetting
- VS.SharePointTools.ContentTypeDesigner.CommonPropertiesPage
- VS.SharePointTools.ListDesigner.CreatingLists
- VS.SharePointTools.ListDesigner.ListPage
- VS.SharePointTools.ListDesigner.ViewPage
- VS.SharePointTools.ListDesigner.CommonPropertiesPage
- VS.SharePointTools.ContentTypeDesigner.ColumnsPage
dev_langs:
- VB
- CSharp
ms.assetid: 9ceed263-3aec-41dc-8708-63cb37a08fa8
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5f111efa5c2276adcc76fdf13cdf5a805929c63
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-site-columns-content-types-and-lists-for-sharepoint"></a>SharePoint için Site Sütunları, İçerik Türleri ve Listeler Oluşturma
  Visual Studio Proje öğesi şablonları dahil olmak üzere birçok farklı temel SharePoint öğeleri için sağlar *listeler* ve *içerik türlerine*, her ikisi de site sütunları dahil edebilirsiniz (veya  *alanları*). İçerik türleri ve listeler için yeni tasarımcıları bu öğelerin her zamankinden daha kolay oluşturma olun.  
  
## <a name="site-columns"></a>Site sütunları  
 Site sütunları bir SharePoint projesine ekleyebileceğiniz en temel öğeleri biridir. Bir site sütunu, bir telefon numarası, açıklama veya bir kişinin bir kişi listesinde şehir adı gibi veri türünü temsil eder.  
  
 Yeni site sütunu proje öğesi şablonu oluşturma site sütunları Visual Studio'nun önceki sürümünde daha kolay hale getirir. Yeni bir site sütunu oluşturduktan sonra site sütunun Elements.xml dosyasındaki XML görünen adını, veri türünü ve site sütunu SharePoint'te görüntülenmesini istediğiniz grubu gibi istediğiniz bilgileri içerecek şekilde değiştirebilirsiniz. Site sütunları hakkında daha fazla bilgi için bkz: [sütunları giriş](http://go.microsoft.com/fwlink/?LinkId=224996).  
  
## <a name="content-types-and-lists"></a>İçerik türleri ve listeler  
 İçerik türleri ve listeler arasında en sık kullanılan SharePoint öğelerdir.  
  
 Bir içerik türü, bir SharePoint liste veya belge kitaplığında meta verileri, iş akışı ve bir kategori öğesi davranışını tanımlar. Örneğin, bir içerik türü için bilgi kişiler listesi veya bir görev listesi oluşturabilirsiniz. Kişi bir içerik türü adı, e-posta, telefon numarasını ve adresi gibi sütunları içerebilir. Site düzeyinde tanımlayan bir içerik türü, herhangi bir liste veya belge kitaplığı sitedeki bağımsızdır. Farklı listeler veya SharePoint sitesinde belge kitaplıkları ile aynı içerik türü kullanabilirsiniz. Çeşitli içerik türleri aynı liste veya belge kitaplığı üzerinde de kullanabilirsiniz.  
  
 Bir liste, başkalarıyla paylaşabilirsiniz SharePoint bilgi koleksiyonudur. Listeleri veriler içeren sütunların satırlarını oluşur. Listeleri bazı örnekler şunlardır: görev listesi, kişiler listesi ve bir duyuru listesi.  
  
 Yeni içerik türü ve liste tasarımcılarına [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] çok daha kolay ve daha sezgisel Visual Studio'nun önceki sürümünde site içerik türleri ve listeler oluşturma olun. Kullanıcı arabirimini görsel olarak bilinen bir biçimde içerik türleri ve listeler oluşturmanıza olanak sağlar ve sıralama ve listelerindeki verileri gruplandırmak ve grup başlıklarını kullanmanıza olanak tanır. İçerik türleri hakkında daha fazla bilgi için bkz: [içerik türleri](http://go.microsoft.com/fwlink/?LinkId=224997). Listeleri hakkında daha fazla bilgi için bkz: [liste formları](http://go.microsoft.com/fwlink/?LinkId=224998) ve [liste görünümleri](http://go.microsoft.com/fwlink/?LinkId=224999).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[İzlenecek yol: bir Site sütunu, içerik türü ve SharePoint listesi oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Özel bir içerik türünde kullanılan site sütunları oluşturulacağını gösterir. İçerik türü sonra özel bir liste kullanılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint 2010'Geliştirmeye Başlarken](http://go.microsoft.com/fwlink/?LinkId=225000)  
  
  
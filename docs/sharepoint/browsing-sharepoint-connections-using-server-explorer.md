---
title: "Sunucu Gezgini kullanarak SharePoint bağlantılarına gözatma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.SharePointExplorer.SharePointConnection
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, browsing SharePoint sites
- SharePoint development in Visual Studio, SharePoint Connections
- SharePoint Connections [SharePoint development in Visual Studio]
ms.assetid: b3b1d97b-e990-414c-8ba5-3fd1b463fbef
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b16a2ee34ca757e62a26676386566b94c31ebf74
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="browsing-sharepoint-connections-using-server-explorer"></a>Sunucu Gezgini Kullanarak SharePoint Bağlantılarına Gözatma
  Yerel SharePoint bağlantıları gözatabilirsiniz **Sunucu Gezgini**. Bu yöntemi kullanarak, bir SharePoint sitesi bileşenleriyle sisteminizde gidebilirsiniz. Liste tanımları ve içerik türleri gibi SharePoint site bileşenlerini adlı bir düğüm görünür **SharePoint bağlantıları** ağaç görünümünde **Sunucu Gezgini**. Görüntülenecek **Sunucu Gezgini**, menü çubuğunda seçin **Görünüm**, **Sunucu Gezgini**. SharePoint site bileşenlerini görüntüleme ek olarak, öğeleri kaldırmak, özelliklerini görüntülemek veya kısayol menüsünden komutları kullanarak ağaç görünümü yenileyin.  
  
> [!IMPORTANT]  
>  Bir SharePoint sitesine göz atmak için SharePoint site koleksiyonunun bir yönetici olması ve Visual Studio'yı bir yerel bilgisayarda yönetici olarak çalıştırıyor olmanız gerekir. Site Aksi takdirde görünür **Sunucu Gezgini**, ancak, düğüm genişletilemiyor. Site koleksiyonu yöneticisi olup olmadığını doğrulamak için siteyi bir web tarayıcısında Aç Aç **Site eylemleri** menüsünde seçin **Site izinleri**ve ardından **izinleri: Takım Site** sayfasında, **Site koleksiyonu yöneticileri** komutunu **Yönet** Şerit üzerindeki Grup. Site koleksiyonu yöneticisi varsa adınızı metin kutusunda görüntülenir. Varsa **Site koleksiyonu yöneticileri** komutu Şerit üzerindeki Yönet grubundaki görünmüyor, site koleksiyonu için bir yönetici değil ve site yöneticisinden uygun izinleri almak gerekir.  
  
## <a name="server-explorer-nodes"></a>Sunucu Gezgini düğümleri  
 Her bir SharePoint sitesi bileşeninin bir düğüm tarafından temsil edilen **Sunucu Gezgini** ağaç görünümü altında **SharePoint bağlantıları**. Örneğin, varsayılan SharePoint siteleri görüntüler bir tartışma türünü temsil eder tartışma adlı bir içerik türü dahil **tartışmalara** SharePoint sitesi sayfası. Tartışma içerik türü birden fazla alan içeriyor. Bu alanları görüntülemek için **Sunucu Gezgini**, genişletin **içerik türü** düğümünü ve ardından **tartışma** düğümü. Altında olan gövdesi, tartışma konu ve başlık gibi birkaç alan düğümü.  
  
## <a name="node-shortcut-menu-commands"></a>Düğüm kısayol menü komutları  
 Her düğüm düğümünü sağ tıklayarak veya onu seçme ve SHIFT + F10 tuşlarına basarak anahtarları seçme erişim bir kısayol menüsünde vardır. Düğüm komutları aşağıdakileri içerebilir:  
  
|Komut adı|Açıklama|  
|------------------|-----------------|  
|Yenile|Ağaç görünümü düğümünde görüntülenen son tarihten oluşmuş olabilecek değişiklikleri yansıtacak şekilde güncelleştirir.|  
|Sil|Seçili düğümün ağaç görünümünden kaldırır. **Not:** bu komut yalnızca altında listelenen SharePoint bağlantıları etkin **SharePoint bağlantıları** düğümü.|  
|Özellikler|Seçili konumda kullanılabilir özelliklerini görüntüler **özellikleri** penceresi. Salt okunur tüm özellikleri ve her düğümün kendisiyle ilişkili özellikler vardır.|  
|Bağlantı Ekle|Gözatmak istediğiniz bir SharePoint sitesi belirtmenize olanak tanır. Kullanılabilir **SharePoint bağlantıları** düğümünü ve alt site düğümleri.|  
|Tarayıcıda görüntüle|Seçilen Liste Web tarayıcısında görüntüler. Bu komut altında bazı listelerde kullanılabilir **listeler** bulunan düğüm **listeler ve kitaplıklar**.|  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: SharePoint Bağlantıları Ekleme veya Kaldırma](../sharepoint/how-to-add-or-remove-sharepoint-connections.md)|Yeni bir SharePoint sitesi eklemek için gereken adımları açıklar **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  
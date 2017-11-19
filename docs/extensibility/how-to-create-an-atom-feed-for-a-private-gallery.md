---
title: "Nasıl yapılır: bir Atom oluşturmak için özel Galerisi akışı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b41cb3012b937ac5448b129657064cca68a5d725
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Nasıl yapılır: bir Atom oluşturmak için özel Galerisi akışı
Bir Atom (uzantılarını içerir ve akışına ekleyen bir intranet konumu için RSS akışı) oluşturabileceğiniz **Uzantılar ve güncelleştirmeler** Özel Galeri olarak. Daha fazla bilgi için bkz: [özel galerileri](../extensibility/private-galleries.md).  
  
## <a name="creating-an-atom-feed"></a>Atom oluşturma akış  
 Atom akışı özel bir galeri oluşturmak için önce bir klasöre uzantılarınızın (.vsix dosyaları) toplamanız gerekir. İsterseniz, alt klasörler halinde düzenleyebilirsiniz. Aşağıdaki kaynaklar de gerekir:  
  
-   Uzantıları özel bir Galerisi tarafından kullanılabilmesini atom.xml dosyası. Atom.xml dosyasına bağlanma hakkında bilgi için **Uzantılar ve güncelleştirmeler**, bkz: [özel galerileri](../extensibility/private-galleries.md).  
  
-   Uzantıları (örneğin, ekran görüntüleri) ayıklanmış tüm resim dosyaları içeren klasör. Kullanılabilir; böylece bu görüntüleri için göreli bağlantıları atom.xml dosyayı içeren **Uzantılar ve güncelleştirmeler**.  
  
 Örneğin, bir klasöre toplanan aşağıdaki iki uzantıları varsayın:  
  
-   Template_Wizard_239.vsix boş bir VSIX proje şablonudur.  
  
-   SelectionHighlight.vsix Seçili sözcüğün tüm örneklerini vurgulamak için bir araçtır.  
  
 Aşağıdaki örnek atom.xml dosyasının içeriğini benzeyecektir:  
  
```  
  <?xml version="1.0" encoding="utf-8" ?>   
- <feed xmlns="http://www.w3.org/2005/Atom">  
  <title type="text" />   
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>   
  <updated>2011-04-14T21:25:48Z</updated>   
- <entry>  
  <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>   
  <title type="text">Highlight all occurrences of selected word</title>   
  <summary type="text">This extends the editor to highlight ....</summary>   
  <published>2011-04-14T14:24:51-07:00</published>   
  <updated>2011-04-14T14:24:22-07:00</updated>   
- <author>  
  <name>Microsoft</name>   
  </author>  
  <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />   
  <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />   
  <content type="application/octet-stream" src="SelectionHighlight.vsix" />   
- <Vsix xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010">  
  <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>   
  <Version>1.31</Version>   
  <References />   
  <Rating xsi:nil="true" />   
  <RatingCount xsi:nil="true" />   
  <DownloadCount xsi:nil="true" />   
  </Vsix>  
  </entry>  
- <entry>  
  <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>   
  ...  
  </entry>  
  </feed>  
  
```  
  
 Görüntüleri oluşturulan klasöründeki ekran görüntüleri iki bağlantı etiketlerini bildirim başvurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel galerileri](../extensibility/private-galleries.md)
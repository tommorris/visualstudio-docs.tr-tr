---
title: "Derleme doğrulama testlerinde kod kapsamını çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59c07d15-511e-4fd0-b398-bde9d5ed00d9
caps.latest.revision: "8"
ms.author: douge
manager: douge
ms.openlocfilehash: 3dab1fb335bf1fa7a51faf8f298208c18ec87dc5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="analyzing-code-coverage-in-build-verification-tests"></a>Derleme Doğrulama Testlerinde Kod Kapsamını Çözümleme
Kod kapsamı çözümlemeyi Microsoft Visual Studio kodunuzu ne kadarının otomatikleştirilmiş testleri tarafından kullandı gösterir. Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 Kodunuzda denetlediğinizde, testiniz diğer ekip üyelerinden gelen diğer tüm testlerle birlikte yapı sunucusunda çalışır. (Bu ayarlamış yüklemediyseniz, bkz: [yapı işleminizin testler](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) Tüm proje kapsamı en güncel ve kapsamlı resmini sağladığı için kod kapsamı, Yapı hizmetini çözümlemek kullanışlıdır. Ayrıca, Otomatik Sistem testleri ve geliştirme makinelerde genellikle çalıştırma diğer kodlanmış testleri içerecektir.  
  
1.  Takım Gezgini'nde Aç **derlemeler**ve ardından eklemek veya derleme tanımı düzenleyin.  
  
2.  Üzerinde **işlem** sayfasında **otomatikleştirilmiş testler**, **Test kaynak**, **çalıştırma ayarları**. Ayarlama **çalıştırma ayarlarını dosya türü** için **kod kapsamı etkin**.  
  
     Birden fazla Test Kaynağı tanımı varsa, her biri için bu adımı yineleyin.  
  
    -   *Adında bir alan yok ancak **türü, çalıştırma ayarları dosyası**.*  
  
         Altında **otomatikleştirilmiş testler**seçin **Test derleme** ve üç nokta düğmesini seçin **[...]**  satırın sonundaki. İçinde **Ekle/Düzenle testi** iletişim kutusunda **Test Çalıştırıcısı**, seçin **Visual Studio Test Çalıştırıcısı**.  
  
 ![Derleme tanımı için kod kapsamı ayarlama](../test/media/codecoverage-plaincc.png "CodeCoverage plainCC")  
  
 Yapı çalıştıktan sonra kod kapsamı sonuçları derleme özeti görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Test edildiğini belirlemek ne kadar kodun için kod kapsamını kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)

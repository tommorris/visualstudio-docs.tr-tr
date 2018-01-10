---
title: "Derleme doğrulama testlerinde kod kapsamını çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 3f02166c89837dfd122ab8a8c71913c659ab1dd2
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
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
 [Ne Kadar Kodun Test Edildiğini Belirlemek için Kod Kapsamını Kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)

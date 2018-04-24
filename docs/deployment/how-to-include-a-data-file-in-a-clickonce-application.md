---
title: 'Nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, data
- deploying applications [ClickOnce], data files
- data access, ClickOnce applications
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8240e4bb8ba540fcdd4453e39d9fa6b00b31bef2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-include-a-data-file-in-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulamasına bir Veri Dosyası Dahil Etme
Her [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yüklediğiniz uygulama burada uygulama yönetebilir, kendi veri hedef bilgisayarın yerel disk üzerinde veri dizinine atanır. Veri dosyaları, tüm dosya türlerini içerebilir: metin dosyaları, XML dosyalarını veya hatta Microsoft Access veritabanı (.mdb) dosyaları. Aşağıdaki yordamlar herhangi türde bir veri dosyası ekleme gösterir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
### <a name="to-include-a-data-file-by-using-mageexe"></a>Mage.exe kullanarak bir veri dosyası eklemek için  
  
1.  Uygulamanızın dosyaları geri kalanı ile uygulama dizininize veri dosyası ekleyin.  
  
     Tipik olarak, uygulama dizini dağıtımın geçerli sürümüyle etiketli bir dizin olacaktır — Örneğin, v1.0.0.0.  
  
2.  Uygulama bildiriminizi listesi veri dosyasını güncelleştirin.  
  
     **Mage -u v1.0.0.0\Application.manifest - FromDirectory v1.0.0.0**  
  
     Bu görevi gerçekleştirme uygulama bildiriminizi dosyaların listesini yeniden oluşturur ve karma imzaları da otomatik olarak oluşturur.  
  
3.  Uygulama bildirimini, tercih edilen metin veya XML düzenleyicisinde açın ve Bul `file` öğesi son eklenen dosya için.  
  
     Adlı bir XML dosyası eklediyseniz `Data.xml`, dosya aşağıdaki kod örneğine benzer görünecektir.  
  
 `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Öznitelik Ekle `type` bu öğeye ve bir değeri ile sağlayın `data`.  
  
 `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Uygulama bildiriminizi anahtar çifti ya da sertifika kullanarak yeniden oturum açın ve Dağıtım bildiriminizi yeniden imzalayın.  
  
     Uygulama bildiriminin, karma değiştiğinden Dağıtım bildiriminizi yeniden oturum açmanız gerekir.  
  
     **Mage -s uygulama bildirimi - cf cert_file - pwd parola**  
  
     **Mage -u dağıtım bildirim - appm uygulama bildirimi**  
  
     **Mage -s dağıtım bildirimi - cf SertifikaDosyası - pwd parola**  
  
2.  
  
### <a name="to-include-a-data-file-by-using-mageuiexe"></a>MageUI.exe kullanarak bir veri dosyası eklemek için  
  
1.  Uygulamanızın dosyaları geri kalanı ile uygulama dizininize veri dosyası ekleyin.  
  
2.  Tipik olarak, uygulama dizini dağıtımın geçerli sürümüyle etiketli bir dizin olacaktır — Örneğin, v1.0.0.0.  
  
3.  Üzerinde **dosya** menüsünde tıklatın **açmak** uygulama bildiriminizi açmak için.  
  
4.  Seçin **dosyaları** sekmesi.  
  
5.  Sekmenin üstünde metin kutusuna, uygulamanızın dosyaları içeren dizini girin ve ardından **Populate**.  
  
     Veri dosyanız kılavuzda görüntülenir.  
  
6.  Ayarlama **dosya türü** veri dosyasına değerini **veri**.  
  
7.  Uygulama bildirimini kaydedin ve dosyayı yeniden imzalayın.  
  
     MageUI.exe dosyayı yeniden imzalayın isteyip istemediğinizi sorar.  
  
8.  Dağıtım bildiriminizi yeniden imzalama  
  
     Uygulama bildiriminin, karma değiştiğinden Dağıtım bildiriminizi yeniden oturum açmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarında Yerel ve Uzak Veri Erişimi](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)
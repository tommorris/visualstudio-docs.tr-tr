---
title: "Nasıl yapılır: ClickOnce dağıtım hataları için özel günlük dosyası konumu ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- ClickOnce deployment, error logging
ms.assetid: 77424414-7f0e-4b99-94bb-ea130de92d09
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 4a8ed7ebbd3fc2fc35e9145509ebf335652c4bbd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-set-a-custom-log-file-location-for-clickonce-deployment-errors"></a>Nasıl yapılır: ClickOnce Dağıtım Hataları için Özel Günlük Dosyası Konumu Ayarlama
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]tüm dağıtımlar için etkinlik günlük dosyalarını korur. Bu günlükler yükleme ve başlatılmasına bağlı tüm hataları belgeler bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım. Varsayılan olarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] her dağıtım etkinleştirme için bir günlük dosyası oluşturur. Bu günlük dosyaları geçici Internet dosyaları klasöründe depolar. Bir dağıtım için günlük dosyası kullanıcıya bir etkinleştirme hatası oluşur ve kullanıcının tıkladığında görüntülenir **ayrıntıları** ortaya çıkan hata iletişim kutusunda.  
  
 Kayıt Defteri Düzenleyicisi'ni kullanarak belirli bir istemci için bu davranışı değiştirebilirsiniz (**regedit.exe**) bir özel günlük dosyası yolu ayarlamak üzere. Bu durumda, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] etkinleştirme başarı ve başarısızlık tüm dağıtımlar için tek bir dosyaya kaydeder.  
  
> [!CAUTION]
>  Kayıt Defteri Düzenleyicisi'ni yanlış kullanırsanız, işletim sisteminizi yeniden yüklemenizi gerektirebilecek önemli sorunlara neden olabilir. Kayıt Defteri Düzenleyicisi'ni kullanmak, kendi sorumluluğunuzdadır.  
  
> [!NOTE]
>  Kesmek veya bazen çok fazla büyümesini engellemek için günlük dosyasını silmek gerekir.  
  
 Aşağıdaki yordamda, tek bir istemci için özel günlük dosyası konumu ayarlama açıklanmaktadır.  
  
### <a name="to-set-a-custom-log-file-location"></a>Özel günlük dosyası konumu ayarlamak için  
  
1.  Açık **Regedit.exe**.  
  
2.  Düğümüne gidin `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  Dize değeri ayarlayın `LogFilePath` tam yolunu ve dosya adı, tercih edilen özel günlük konum.  
  
     Bu konum, kullanıcı yazma erişimi olan bir dizin olmalıdır. Örneğin, Windows Vista, aşağıdaki klasör yapısını oluşturun ve ayarlayın `LogFilePath` C:\Users için\\< kullanıcı adı\>\Documents\Logs\ClickOnce\installation.log.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım sorunlarını giderme](../deployment/troubleshooting-clickonce-deployments.md)
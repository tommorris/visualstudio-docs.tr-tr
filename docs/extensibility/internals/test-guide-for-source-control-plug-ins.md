---
title: Test kaynak denetimi eklentiler için Kılavuzu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 37af6a289b59b6066a71836e4d44e380b584ec70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="test-guide-for-source-control-plug-ins"></a>Kaynak denetimi eklentiler için test Kılavuzu
Bu bölümde, kaynak denetim eklentisi ile test etmek için yönergeler sağlanmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. En yaygın test alanları yanı sıra bazı sorunlu olabilecek daha karmaşık alanlar kapsamlı bir bakış sağlanır. Bu genel bakışta test çalışmalarının kapsamlı bir liste olması düşünülmemiştir.  
  
> [!NOTE]
>  Bazı hata düzeltmeleri ve en son geliştirmeleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE mevcut kaynak denetim daha önce önceki sürümlerini kullanırken karşılaşılan değil eklentileri sorunları ortaya çıkarmaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Hiçbir eklenti için önceki sürümü bu yana yapılan değişiklikler olsa bile bu bölümde, numaralandırılmış alanlar için eklenti, mevcut kaynak denetimi test kesinlikle önerilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="common-preparation"></a>Ortak hazırlama  
 Bir makine [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve yüklü, hedef kaynak denetim eklentisi gereklidir. Benzer şekilde yapılandırılmış ikinci bir makine açık kaynak denetimi testlerden bazıları için kullanılabilir.  
  
## <a name="definition-of-terms"></a>Terimlerin tanımı  
 Bu test Kılavuzu amacıyla aşağıdaki terim tanımları kullanın:  
  
 İstemci projesi  
 Herhangi bir proje türü kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetimi tümleştirmesinin destekleyen (örneğin, [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], veya [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]).  
  
 Web projesi  
 Web projeleri dört tür vardır: dosya sistemi, yerel IIS, uzak siteleri ve FTP.  
  
-   Dosya sistemi projeleri bir yerel yol oluşturulur, ancak dahili bir UNC yolu erişilen ve istemci projeleri benzediğini IDE içinde kaynak denetiminden altına yerleştirilmiş olarak yüklenmesi için Internet Information Services (IIS) gerektirmez.  
  
-   Yerel IIS projeleri aynı makinede yüklü olduğundan ve erişilen IIS yerel makineye işaret eden bir URL ile birlikte çalışın.  
  
-   Uzak siteleri projeleri Ayrıca IIS hizmetleri altında oluşturulan, ancak IIS server makinesinde ve değil, kaynak denetimindeki yerleştirilen içinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
-   FTP projeleri uzak bir FTP sunucusu üzerinden erişilen ancak kaynak denetimi altında yerleştirilemez.  
  
 Kaydı  
 Çözüm ya da kaynak denetimi altında proje için başka bir terim.  
  
 Sürüm deposu  
 Kaynak Denetim eklentisi API aracılığıyla erişilen kaynak denetim veritabanı.  
  
## <a name="test-areas-covered-in-this-section"></a>Bu bölümde yer alan test alanları  
  
-   [Test alanı 1: Kaynak denetiminden Aç / ekleyin](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    -   Case 1a: kaynak denetimine Çözüm Ekle  
  
    -   Case 1b: kaynak denetiminden çözümü açın  
  
    -   Case 1c: kaynak denetiminden çözüme ekleyin  
  
-   [Test Alanı 2: Kaynak Denetiminden Alma](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
-   [Test alanı 3: Kullanıma / kullanıma almayı geri al](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    -   Durum 3: Kullanıma / kullanıma almayı geri al  
  
    -   Case 3a: gözden geçirin  
  
    -   Case 3b: Checkout bağlantısı kesildi  
  
    -   Case 3c: Sorgu düzenleme/sorguyu kaydetmek (QEQS)  
  
    -   3B case: Sessiz kullanıma alma  
  
    -   Case 3e: kullanıma almayı geri alma  
  
-   [Test Alanı 4: İade Etme](../../extensibility/internals/test-area-4-check-in.md)  
  
    -   Case 4a: öğeler  
  
    -   Case 4b: dosya ekleme  
  
    -   Bu durumda 4 c: projelerine ekleme  
  
-   [Test Alanı 5: Kaynak Denetimini Değiştirme](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    -   Case 5a: bağlama  
  
    -   Case 5b: bağlantı kesme  
  
    -   Case 5c: yeniden bağlayın  
  
-   [Test Alanı 6: Silme](../../extensibility/internals/test-area-6-delete.md)  
  
-   [Test Alanı 7: Paylaşma](../../extensibility/internals/test-area-7-share.md)  
  
-   [Test Alanı 8: Eklenti Değiştirme](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    -   Case 8a: otomatik değiştirme  
  
    -   Case 8b: Çözüm tabanlı Değiştir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri](../../extensibility/source-control-plug-ins.md)
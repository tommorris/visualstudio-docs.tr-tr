---
title: Kaynak Denetim Eklentileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, reference
ms.assetid: 964980ca-21c5-4706-8535-6ea23e1c9cc9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a3395275938d78178f6f39ccd0f67dca01194bcc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140222"
---
# <a name="source-control-plug-ins"></a>Kaynak Denetim Eklentileri
Kaynak Denetim eklentisi SDK başvurusu bölümü kaynak denetim sistemleri ile tümleştirilmesini sağlar tam arabirim belirtimi içeriyor [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kaynak Denetim eklentisi arabirimi uygulamalıdır çeşitli işlevleri ve veri türlerini semantiği ve sözdizimi belirtir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)  
 Kaynak Denetimi Eklentisi tarafından kaynak denetim eklentisi API'si ile uymak için uygulanması gereken işlevleri listeler.  
  
 [IDE Tarafından Uygulanan Geri Çağırma İşlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)  
 Bazı komutlar yürütülürken IDE bilgi geçirmek için kaynak denetim eklentisi kullanır işlevleri açıklanmaktadır.  
  
 [Numaralandırıcılar](../extensibility/enumerators.md)  
 Kaynak Denetim eklentisi hakkında bilmeniz gereken kaynak denetim eklentisi API'sindeki Numaralandırıcı veri türlerini listeler.  
  
 [Özellik Bayrakları](../extensibility/capability-flags.md)  
 Açıklar `SCC_CAP_xxx` bir sağlayıcının özellikleri gösteren bayrak.  
  
 [Özel Komutlar Tarafından Kullanılan Bit Bayrakları](../extensibility/bitflags-used-by-specific-commands.md)  
 Belirli komutların bağlamda yararlı bayrakları listeler.  
  
 [Hata Kodları](../extensibility/error-codes.md)  
 Listeleri olarak işlev tarafından döndürülen genel hata değerlerini `SCCTRN`.  
  
 [Kaynak Denetimi Eklentisi Bulmak için Anahtar Olarak Kullanılan Dizeler](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)  
 Kaynak denetimi eklenti bulmak için kayıt defteri erişim tuşları açıklanmaktadır.  
  
 [MSSCCPRJ.SCC Dosyası](../extensibility/mssccprj-scc-file.md)  
 Bilgi IDE donuk içeriyor, ancak, kaynak denetimi eklentisi tarafından sürüm denetimindeki proje ve çözüm bulmak için kullanılan bir istemci-tarafı dosya tanımlar.  
  
 [Kaynak Denetimi Eklentisi Uygulamak için En İyi Yöntemler](../extensibility/best-practices-for-implementing-a-source-control-plug-in.md)  
 Kaynak Denetim eklentisi API uygulama sırada anımsaması önemli teknik anımsatıcıları koleksiyonu sağlar.  
  
 [Dize Uzunluğu Kısıtlamaları](../extensibility/restrictions-on-string-lengths.md)  
 Kaynak Denetim eklentisi API sınırlamaları çeşitli işlevlerde kullanılan dizeleri uzunlukları açıklar.  
  
 [Sözlük](../extensibility/source-control-plug-in-glossary.md)  
 Yararlı hüküm ve kaynak denetimi eklentisi SDK belgeleri okumak için tanımlarını sağlar.  
  
 [Nasıl Yapılır: Kaynak Denetimi Eklentileri için Uyumluluk Uyarılarını Kapatma](../extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins.md)  
 Uyarıları devre dışı bırakmak açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetim eklenti örneği](http://msdn.microsoft.com/en-us/61de7d2b-71db-451e-8e3e-d41b11c7a4ca)  
 Kaynak denetimi eklenti işlevlerinin bir örnek sağlar.  
  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Kaynak denetimi eklentisi ile ilgili sınama yordamları açıklar.  
  
 [Kaynak Denetimi Eklentisi Oluşturma](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Kaynak denetimi işlevlerinin kullanırken sağlayan bir kaynak denetimi eklenti oluşturmak nasıl ele [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kaynak denetimi kullanıcı arabirimini (UI).  
  
 [Visual Studio SDK Başvurusu](../extensibility/visual-studio-sdk-reference.md)  
 Başvuru konuları listesini gösterir.
---
title: Kaynak Denetim Eklentileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, reference
ms.assetid: 964980ca-21c5-4706-8535-6ea23e1c9cc9
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea5169b3d74a77bbb079dab5b310a3b7ebbbeff0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="source-control-plug-ins"></a>Kaynak Denetim Eklentileri
Kaynak Denetim eklentisi SDK başvurusu bölümü kaynak denetim sistemleri ile tümleştirilmesini sağlar tam arabirim belirtimi içeriyor [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kaynak Denetim eklentisi arabirimi uygulamalıdır çeşitli işlevleri ve veri türlerini semantiği ve sözdizimi belirtir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)  
 Kaynak Denetimi Eklentisi tarafından kaynak denetim eklentisi API'si ile uymak için uygulanması gereken işlevleri listeler.  
  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)  
 Bazı komutlar yürütülürken IDE bilgi geçirmek için kaynak denetim eklentisi kullanır işlevleri açıklanmaktadır.  
  
 [Numaralandırmalar](../extensibility/enumerators.md)  
 Kaynak Denetim eklentisi hakkında bilmeniz gereken kaynak denetim eklentisi API'sindeki Numaralandırıcı veri türlerini listeler.  
  
 [Yetenek bayrakları](../extensibility/capability-flags.md)  
 Açıklar `SCC_CAP_xxx` bir sağlayıcının özellikleri gösteren bayrak.  
  
 [Özel komutlar tarafından kullanılan bit işaretleri](../extensibility/bitflags-used-by-specific-commands.md)  
 Belirli komutların bağlamda yararlı bayrakları listeler.  
  
 [Hata kodları](../extensibility/error-codes.md)  
 Listeleri olarak işlev tarafından döndürülen genel hata değerlerini `SCCTRN`.  
  
 [Kaynak denetimi eklenti bulmak için anahtar olarak kullanılan dizeleri](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)  
 Kaynak denetimi eklenti bulmak için kayıt defteri erişim tuşları açıklanmaktadır.  
  
 [MSSCCPRJ. SCC dosyası](../extensibility/mssccprj-scc-file.md)  
 Bilgi IDE donuk içeriyor, ancak, kaynak denetimi eklentisi tarafından sürüm denetimindeki proje ve çözüm bulmak için kullanılan bir istemci-tarafı dosya tanımlar.  
  
 [Kaynak Denetim eklentisi uygulamak için en iyi yöntemler](../extensibility/best-practices-for-implementing-a-source-control-plug-in.md)  
 Kaynak Denetim eklentisi API uygulama sırada anımsaması önemli teknik anımsatıcıları koleksiyonu sağlar.  
  
 [Dize uzunluğu kısıtlamalar](../extensibility/restrictions-on-string-lengths.md)  
 Kaynak Denetim eklentisi API sınırlamaları çeşitli işlevlerde kullanılan dizeleri uzunlukları açıklar.  
  
 [Sözlük](../extensibility/source-control-plug-in-glossary.md)  
 Yararlı hüküm ve kaynak denetimi eklentisi SDK belgeleri okumak için tanımlarını sağlar.  
  
 [Nasıl yapılır: kaynak denetimi eklentiler için uyumluluk uyarılarını devre dışı bırakma](../extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins.md)  
 Uyarıları devre dışı bırakmak açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetim eklenti örneği](http://msdn.microsoft.com/en-us/61de7d2b-71db-451e-8e3e-d41b11c7a4ca)  
 Kaynak denetimi eklenti işlevlerinin bir örnek sağlar.  
  
 [Kaynak denetimi eklentiler için test Kılavuzu](../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Kaynak denetimi eklentisi ile ilgili sınama yordamları açıklar.  
  
 [Kaynak Denetimi Eklentisi oluşturma](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Kaynak denetimi işlevlerinin kullanırken sağlayan bir kaynak denetimi eklenti oluşturmak nasıl ele [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kaynak denetimi kullanıcı arabirimini (UI).  
  
 [Visual Studio SDK'sı başvurusu](../extensibility/visual-studio-sdk-reference.md)  
 Başvuru konuları listesini gösterir.
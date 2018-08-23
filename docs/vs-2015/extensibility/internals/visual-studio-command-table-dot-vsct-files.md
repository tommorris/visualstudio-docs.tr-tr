---
title: Visual Studio komut tablosu (. Vsct) dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0692f0b32544edf7d5d7cec4b0ab4592c4219b3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686536"
---
# <a name="visual-studio-command-table-vsct-files"></a>Visual Studio Komut Tablosu (.Vsct) Dosyaları
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio komut tablosu (. Vsct) dosyaları](https://docs.microsoft.com/visualstudio/extensibility/internals/visual-studio-command-table-dot-vsct-files).  
  
Bir komut tablosu yapılandırma dosyası içeren bir VSPackage'ı komut kümesini tanımlayan bir metin dosyasıdır. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Komut tablosu (VSCT) derleyici XML tabanlı yapılandırma dosyalarını (.vsct) ikili komut tablosu (.cto) çıktı dosyaları derler. Sonuç .cto dosyaları .ctc yapılandırma dosyalarını derlemek için komut tablosu (CTC) derleyiciyi kullanarak oluşturulan aynıdır. Ancak, XML tabanlı .vsct dosyaları, bir XML Düzenleyicisi'ni ve XML IntelliSense'i gibi bazı avantajları vardır.  
  
 .Vsct dosyaları semantiği ve söz dizimi hakkında daha fazla bilgi için bkz: [tasarlama XML komut tablosu (. Vsct) dosyaları](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [XML Komut Tablosu (.Vsct) Dosyaları Tasarlama](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 .Vsct dosyaları tasarlanacağını açıklar.  
  
 [Nasıl Yapılır: .Vsct Dosyası Oluşturma](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 .Vsct dosyası oluşturma yöntemleriyle karşılaştırır. El ile yeni bir .vsct dosyası oluşturma işlemi açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)  
 Komut tablosu XML yapılandırma dosyasını her bir bölümünü hakkında ayrıntılar sağlar.  
  
 [Komut tablosu yapılandırma (. Ctc) dosyaları](http://msdn.microsoft.com/en-us/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Kullanım dışı .ctc dosya biçimi'ne genel bakış sunar.  
  
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Komut tablosu biçim belirtimi açıklar.  
  
 [VSPackage’lardaki Kaynaklar](../../extensibility/internals/resources-in-vspackages.md)  
 Yönetilen ve yönetilmeyen kaynakları yönetilen Vspackage'larda kullanmayı açıklar.  
  
 [Komutlar, Menüler ve Araç Çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Menüleri, araç çubukları ve komut birleşik giriş kutuları içeren bir kullanıcı Arabirimi oluşturma açıklanmaktadır.


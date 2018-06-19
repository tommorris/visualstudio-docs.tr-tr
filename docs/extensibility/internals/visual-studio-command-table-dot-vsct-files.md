---
title: Visual Studio komut tablosu (. Vsct) dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3407c21f242cf45337ddad2ff19993d9e0130fbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140475"
---
# <a name="visual-studio-command-table-vsct-files"></a>Visual Studio komut tablosu (. Vsct) dosyaları
Bir komut tablo yapılandırma dosyası bir VSPackage içeren komut kümesini tanımlayan bir metin dosyasıdır. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tablosu (VSCT) derleyici ikili komutu tablo çıktı (.cto) dosyalarını XML tabanlı yapılandırma dosyaları (.vsct) derler komutu. Sonuç .cto dosyaları .ctc yapılandırma dosyalarını derlemek için komut tablosu (CTC) derleyici kullanılarak oluşturulan aynıdır. Ancak, XML tabanlı .vsct dosyaları, bir XML Düzenleyicisi'ni ve IntelliSense gibi bazı avantajları vardır.  
  
 .Vsct dosyaları semantiği ve sözdizimi hakkında daha fazla bilgi için bkz: [XML komutu tablosu tasarlama (. Vsct) dosyaları](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [XML Komut Tablosu (.Vsct) Dosyaları Tasarlama](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 .Vsct dosyaları tasarım konuları açıklanmaktadır.  
  
 [Nasıl Yapılır: .Vsct Dosyası Oluşturma](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Bir .vsct dosyası oluşturmak için yöntemler karşılaştırır. El ile yeni bir .vsct dosyası oluşturmayı açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)  
 Her komut tablo XML yapılandırma dosyası bölümünü hakkında ayrıntılar sağlar.  
  
 [Komut tablo yapılandırması (. Ctc) dosyaları](http://msdn.microsoft.com/en-us/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Kullanım dışı .ctc dosya biçimi genel bir bakış sunar.  
  
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Komut tablo biçim belirtimi açıklar.  
  
 [VSPackage’lardaki Kaynaklar](../../extensibility/internals/resources-in-vspackages.md)  
 Yönetilen VSPackages yönetilen ve yönetilmeyen kaynakları kullanmayı açıklar.  
  
 [Komutlar, Menüler ve Araç Çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Menüleri, araç çubukları ve komut birleşik giriş kutuları içeren bir kullanıcı Arabirimi oluşturma açıklanmaktadır.
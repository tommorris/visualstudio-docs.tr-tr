---
title: "Visual Studio komut tablosu (. Vsct) dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ace754b9d6ddb220b3647b281011d3763810987c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-command-table-vsct-files"></a>Visual Studio komut tablosu (. Vsct) dosyaları
Bir komut tablo yapılandırma dosyası bir VSPackage içeren komut kümesini tanımlayan bir metin dosyasıdır. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tablosu (VSCT) derleyici ikili komutu tablo çıktı (.cto) dosyalarını XML tabanlı yapılandırma dosyaları (.vsct) derler komutu. Sonuç .cto dosyaları .ctc yapılandırma dosyalarını derlemek için komut tablosu (CTC) derleyici kullanılarak oluşturulan aynıdır. Ancak, XML tabanlı .vsct dosyaları, bir XML Düzenleyicisi'ni ve IntelliSense gibi bazı avantajları vardır.  
  
 .Vsct dosyaları semantiği ve sözdizimi hakkında daha fazla bilgi için bkz: [XML komutu tablosu tasarlama (. Vsct) dosyaları](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [XML komutu tablosu tasarlama (. Vsct) dosyaları](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 .Vsct dosyaları tasarım konuları açıklanmaktadır.  
  
 [Nasıl yapılır: oluşturmak bir. Vsct dosyası](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Bir .vsct dosyası oluşturmak için yöntemler karşılaştırır. El ile yeni bir .vsct dosyası oluşturmayı açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)  
 Her komut tablo XML yapılandırma dosyası bölümünü hakkında ayrıntılar sağlar.  
  
 [Komut tablo yapılandırması (. Ctc) dosyaları](http://msdn.microsoft.com/en-us/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Kullanım dışı .ctc dosya biçimi genel bir bakış sunar.  
  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Komut tablo biçim belirtimi açıklar.  
  
 [VSPackages kaynakları](../../extensibility/internals/resources-in-vspackages.md)  
 Yönetilen VSPackages yönetilen ve yönetilmeyen kaynakları kullanmayı açıklar.  
  
 [Komutları, menüleri ve araç çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Menüleri, araç çubukları ve komut birleşik giriş kutuları içeren bir kullanıcı Arabirimi oluşturma açıklanmaktadır.
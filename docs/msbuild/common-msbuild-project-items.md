---
title: "Yaygın MSBuild proje öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, common project items
ms.assetid: 1eba3721-cc12-4b80-9987-84923ede5e2e
caps.latest.revision: "17"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 82d4687a72cb0f13291aa01ff37b91afbcc254e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="common-msbuild-project-items"></a>Yaygın MSBuild Proje Öğeleri
İçinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bir öğenin bir veya daha fazla adlandırılmış başvurusudur. Meta veri dosya adları, yolları ve sürüm numaraları gibi öğeleri içerir. Tüm türlerinde proje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çeşitli öğeleri genelde sahip. Bu öğeler dosya microsoft.build.commontypes.xsd tanımlanır.  
  
## <a name="common-items"></a>Ortak öğeler  
 Tüm ortak proje öğeleri listesi verilmiştir.  
  
### <a name="reference"></a>Başvuru  
 Proje derleme (yönetilen) başvurusunda temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|HintPath|İsteğe bağlı dize. Derleme göreli veya mutlak yolu.|  
|Ad|İsteğe bağlı dize. Derleme, örneğin, "System.Windows.Forms." görünen adı|  
|FusionName|İsteğe bağlı dize. Öğesi için basit ya da güçlü fusion ad belirtir.<br /><br /> Bu öznitelik mevcut olduğunda, derleme dosyası fusion adı almak için açılacak olmadığından zaman kazanabilirsiniz.|  
|SpecificVersion|İsteğe bağlı Boole değeri. Yalnızca sürüm fusion adında başvuruda bulunup bulunmadığını belirtir.|  
|Diğer adlar|İsteğe bağlı dize. Başvuru için diğer adlar.|  
|Özel|İsteğe bağlı Boole değeri. Başvuru çıkış klasörüne kopyalanır olup olmadığını belirtir. Bu özniteliği ile eşleşen **kopya yerel** Visual Studio IDE içinde olan başvuru özelliği.|  
  
### <a name="comreference"></a>COMReference  
 Bir COM (yönetilmeyen) bileşeni temsil projede başvuru.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|Ad|İsteğe bağlı dize. Bileşen görünen adı.|  
|Guid|İsteğe bağlı dize. {12345678-1234-1234-1234-1234567891234} biçiminde bileşeni için bir GUID.|  
|VersionMajor|İsteğe bağlı dize. Bileşen sürüm numarasını büyük bölümü. Örneğin, "5" tam sürüm numarası "5.46." ise|  
|VersionMinor|İsteğe bağlı dize. Bileşen sürüm numarasını küçük parçası. Örneğin, "46" tam sürüm numarası "5.46." ise|  
|LCID|İsteğe bağlı dize. Bileşeni için LocaleID.|  
|WrapperTool|İsteğe bağlı dize. Bileşen, örneğin, "tlbimp." kullanılan sarmalayıcı aracı adı|  
|Yalıtılmış|İsteğe bağlı Boole değeri. Bileşen reg ücretsiz bir bileşen olup olmadığını belirtir.|  
  
### <a name="comfilereference"></a>COMFileReference  
 ResolvedComreference hedef akış tür kitaplıklarının listesini temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|WrapperTool|İsteğe bağlı dize. Bileşen, örneğin, "tlbimp." kullanılan sarmalayıcı aracı adı|  
  
### <a name="nativereference"></a>NativeReference  
 Yerel bir bildirim dosyası ya da böyle bir dosya için bir başvuru temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|Ad|Gerekli dize. Bildirim dosyasının temel adı.|  
|HintPath|Gerekli dize. Bildirim dosyasının göreli yolu.|  
  
### <a name="projectreference"></a>ProjectReference  
 Başka bir projeye bir başvuru temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|Ad|İsteğe bağlı dize. Başvurunun görünen adı.|  
|Project|İsteğe bağlı dize. {12345678-1234-1234-1234-1234567891234} biçiminde başvurusu için bir GUID.|  
|Paket|İsteğe bağlı dize. Başvurulan proje dosyasının yolu.|  
  
### <a name="compile"></a>Derleme  
 Derleyici için kaynak dosyaları temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|DependentUpon|İsteğe bağlı dize. Bu dosyayı doğru şekilde derlenmesi için bağımlı dosyayı belirtir.|  
|AutoGen|İsteğe bağlı Boole değeri. Dosya için proje tarafından oluşturulup oluşturulmadığını gösterir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE).|  
|Bağlantı|İsteğe bağlı dize. Dosyanın fiziksel olarak proje dosyası etkisi dışında bulunan görüntülenecek notational yolu.|  
|Görünür|İsteğe bağlı Boole değeri. Dosyada görüntülenip görüntülenmeyeceğini gösterir **Çözüm Gezgini** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|İsteğe bağlı dize. Dosyanın çıkış dizinine Kopyala edilip edilmeyeceğini belirler. Değerler şunlardır:<br /><br /> 1.  Hiçbir zaman<br />2.  Her zaman<br />3.  CopyToOutputDirectory|  
  
### <a name="embeddedresource"></a>EmbeddedResource  
 Oluşturulan derlemede katıştırılmış kaynakları temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|DependentUpon|İsteğe bağlı dize. Bu dosyayı doğru şekilde derlenmesi için bağımlı dosyasını belirtir|  
|Oluşturucu|Gerekli dize. Bu öğe üzerinde çalıştırılan tüm dosya oluşturucu adı.|  
|LastGenOutput|Gerekli dize. Bu öğe üzerinde çalışan herhangi bir dosya Oluşturucu tarafından oluşturulan dosya adı.|  
|CustomToolNamespace|Gerekli dize. Tüm bu öğe üzerinde çalışan Oluşturucu dosya ad alanı kodu oluşturmanız gerekir.|  
|Bağlantı|İsteğe bağlı dize. Notational yolu, dosya proje etkisi dışında fiziksel olarak bulunuyorsa görüntülenir.|  
|Görünür|İsteğe bağlı Boole değeri. Dosyada görüntülenip görüntülenmeyeceğini gösterir **Çözüm Gezgini** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|İsteğe bağlı dize. Dosyanın çıkış dizinine Kopyala edilip edilmeyeceğini belirler. Değerler şunlardır:<br /><br /> 1.  Hiçbir zaman<br />2.  Her zaman<br />3.  CopyToOutputDirectory|  
|LogicalName|Gerekli dize. Katıştırılmış kaynak mantıksal adı.|  
  
### <a name="content"></a>İçerik  
 Projeye derlenmemiş ancak katıştırılmış veya olabilir, birlikte yayımlanan dosyaları temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|DependentUpon|İsteğe bağlı dize. Bu dosyayı doğru şekilde derlenmesi için bağımlı dosyayı belirtir.|  
|Oluşturucu|Gerekli dize. Bu öğe üzerinde çalışan tüm dosya oluşturucu adı.|  
|LastGenOutput|Gerekli dize. Bu öğe üzerinde çalıştırıldığı herhangi dosya Oluşturucu tarafından oluşturulan dosya adı.|  
|CustomToolNamespace|Gerekli dize. Tüm bu öğe üzerinde çalışan Oluşturucu dosya ad alanı kodu oluşturmanız gerekir.|  
|Bağlantı|İsteğe bağlı dize. Dosyası projeye etkisini dışında fiziksel olarak bulunuyorsa görüntülenecek notational yolu.|  
|PublishState|Gerekli dize. İçerik Yayımlama durumu ya da:<br /><br /> -Varsayılan<br />-Dahil<br />-Dışlanan<br />-Veri dosyası<br />-Önkoşulu|  
|IsAssembly|İsteğe bağlı Boole değeri. Dosyanın derleme olup olmadığını belirtir.|  
|Görünür|İsteğe bağlı Boole değeri. Dosyada görüntülenip görüntülenmeyeceğini gösterir **Çözüm Gezgini** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|İsteğe bağlı dize. Dosyanın çıkış dizinine Kopyala edilip edilmeyeceğini belirler. Değerler şunlardır:<br /><br /> 1.  Hiçbir zaman<br />2.  Her zaman<br />3.  CopyToOutputDirectory|  
  
### <a name="none"></a>Yok.  
 Herhangi bir rol yapı işleminde sahip olması gereken dosyaları temsil eder.  
  
|Öğe adı|Açıklama|  
|---------------|-----------------|  
|DependentUpon|İsteğe bağlı dize. Bu dosyayı doğru şekilde derlenmesi için bağımlı dosyayı belirtir.|  
|Oluşturucu|Gerekli dize. Bu öğe üzerinde çalıştırılan tüm dosya oluşturucu adı.|  
|LastGenOutput|Gerekli dize. Bu öğe üzerinde çalışan herhangi bir dosya Oluşturucu tarafından oluşturulan dosya adı.|  
|CustomToolNamespace|Gerekli dize. Tüm bu öğe üzerinde çalışan Oluşturucu dosya ad alanı kodu oluşturmanız gerekir.|  
|Bağlantı|İsteğe bağlı dize. Dosyası projeye etkisini dışında fiziksel olarak bulunuyorsa görüntülenecek notational yolu.|  
|Görünür|İsteğe bağlı Boole değeri. Dosyada görüntülenip görüntülenmeyeceğini gösterir **Çözüm Gezgini** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|İsteğe bağlı dize. Dosyanın çıkış dizinine Kopyala edilip edilmeyeceğini belirler. Değerler şunlardır:<br /><br /> 1.  Hiçbir zaman<br />2.  Her zaman<br />3.  CopyToOutputDirectory|  
  
### <a name="baseapplicationmanifest"></a>BaseApplicationManifest  
 Yapı için temel uygulama bildirimini temsil eder ve içeren [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım güvenlik bilgileri.  
  
### <a name="codeanalysisimport"></a>CodeAnalysisImport  
 İçeri aktarmak için FxCop proje temsil eder.  
  
### <a name="import"></a>İçeri aktarma  
 Derlemeleri olan ad alanları aktarılacaksa tarafından temsil [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derleyici.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yaygın MSBuild proje özellikleri](../msbuild/common-msbuild-project-properties.md)

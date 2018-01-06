---
title: "VSIX Dil Paketi Şeması 2.0 başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
caps.latest.revision: "8"
ms.author: dagriffe
author: dgriffen
manager: ghogen
ms.workload: dagriffe
ms.openlocfilehash: b601653e4b2d309d41f32ff71666567ab860e698
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vsix-language-pack-schema-20-reference"></a>VSIX Dil Paketi 2.0 şema başvurusu

VSIX Dil Paketi şema VSIX paket için yerelleştirilmiş yükleme bilgilerini sağlar. Bu şemayı 2.0 sürümünü ek yerelleştirme öğeleri destekler.

## <a name="language-pack-schema"></a>Dil Paketi şeması

Dil paketi dosyasının kök öğesinin `<PackageLanguagePackManifest>`, özniteliği ile `Version`, dil paketi biçimi sürümünü olduğu. Bu konu ayarlayarak bildiriminde belirtilen dil paketi biçiminde 2.0 sürümünü açıklar `Version` özniteliği değerine `Version="2.0.0"`. Tam olarak bir alt kök öğe içeriyor `<Metadata>` öğesi.

### <a name="packagelangaugepackmanifest-element"></a>PackageLangaugePackManifest öğesi

İçinde `<PackageLanguagePackManifest>` öğesi öğesi bulunmalıdır:
|Başlık|Açıklama|
|-----------|-----------------|
|`<Metadata>`| Tüm yerelleştirilmiş paket meta verileri içeren öğe

### <a name="metadata-element"></a>Meta veri öğesi

İçinde `<Metadata>` öğesi şu öğeleri sahip olabilir:
|Başlık|Açıklama|
|-----------|-----------------|
|`<DisplayName>`|Yüklenecek uzantısı yerelleştirilmiş adı|
|`<Description>`|Yüklenecek uzantısı yerelleştirilmiş açıklaması|
|`<License>`| Uzantının lisans yerelleştirilmiş bir sürümün bir yolu|
|`<MoreInfo>`| Uzantı hakkında yerelleştirilmiş bilgilere bağlantı|
|`<ReleaseNotes>`| Bir yolu veya Sürüm notlarının yerelleştirilmiş bir sürümün Bağla|
|`<Icon>`| Uzantıları simgesinin yerelleştirilmiş bir sürümün bir yolu|

### <a name="sample-manifest"></a>Örnek bildirimi

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</LocalizedName>
    <Description> Esta extensión pone control personalizado en la caja de herramientas por manejar información de familia.</Description>
    <MoreInfo> http://www.contoso.com/products/es/ArbolDeFamilia.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
</PackageLanguagePackManifest>
```

## <a name="see-also"></a>Ayrıca Bkz.

|Başlık|Açıklama|
|-----------|-----------------|
|[VSIX Paketlerini Yerelleştirme](../extensibility/localizing-vsix-packages.md)|VSIX paketi için yerelleştirilmiş yükleme desteği sağlamak üzere nasıl gösterir.|
|[VSIX Uzantı Şeması 2.0 Başvurusu](../extensibility/vsix-extension-schema-2-0-reference.md)|VSIX bildirim kullanılarak yüklenmesi Visual Studio uzantısını etkinleştirir .vsix dağıtım dosyasının içeriğini açıklayan **Uzantılar ve güncelleştirmeler** iletişim kutusu.|
|[Visual Studio Uzantıları’nı bulma ve kullanma](../ide/finding-and-using-visual-studio-extensions.md)|Nasıl kullanılacağını gösterir **Uzantılar ve güncelleştirmeler** yüklemek, kaldırmak, etkinleştirme ve uzantıları devre dışı bırakmak için iletişim kutusu.|
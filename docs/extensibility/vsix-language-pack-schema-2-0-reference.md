---
title: VSIX Dil Paketi Şeması 2.0 başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: dagriffe
author: dgriffen
manager: douge
ms.workload:
- dagriffe
ms.openlocfilehash: 571f90f31014dcc4d5686483bfc037e458f4a31e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
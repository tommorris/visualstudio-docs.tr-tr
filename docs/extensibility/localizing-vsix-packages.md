---
title: "VSIX paket yerelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localize package
- localize extension
- localized deployment
ms.assetid: 10e80b13-b39e-466c-a7c8-774a862355af
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a8bb9332b30e5dbc410bdacea3800713b25b10f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="localizing-vsix-packages"></a>VSIX paket yerelleştirme

Her hedef dil için bir Extension.vsixlangpack dosyası oluşturarak ve bunları doğru klasöre koyma VSIX paketi yerelleştirebilirsiniz. Yerelleştirilmiş paketi yüklendiğinde, yerelleştirilmiş adı uzantısının yerelleştirilmiş açıklama ile birlikte görüntülenir. Yerelleştirilmiş lisans dosyası ya da yerelleştirilmiş bilgilere işaret eden bir URL sağlarsanız, bunlar da görüntülenir.

İçerik ekler VSPackage VSIX paketi içeriyorsa menü komutları veya diğer UI bakın [yerelleştirme menü komutlarını](../extensibility/localizing-menu-commands.md) yeni kullanıcı Arabirimi öğelerini yerelleştirme hakkında bilgi.

## <a name="directory-structure"></a>Dizin yapısı

 Bir kullanıcı bir uzantı yüklendiğinde **Uzantılar ve güncelleştirmeler** VSIX paket adı ile eşleşen hedef bilgisayarın Visual Studio yerel bir klasör için üst düzey denetler. Varsa **Uzantılar ve güncelleştirmeler** .vsixlangpack bir bulursa dosya klasöründe, bu dosya .vsixmanifest dosyasında karşılık gelen değerler için yerelleştirilmiş değerleri değiştirir. Bu değerleri uzantısı yüklü olduğunda görüntülenir. Aşağıdaki örnek, İspanyolca (es-ES) ve Fransızca (fr-FR) halinde yerelleştirilmiş bir VSIX paket için dizin yapısını gösterir.  

```text
.
├── MyExtension.dll
├── Extension.vsixmanifest
├── [Content_Types].xml
├── es-ES
│   └── Extension.vsixlangpack
└── fr-FR
    └── Extension.vsixlangpack
```

> [!NOTE]
> Desteklenen VSIX proje şablonlarını [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] VSIX bildirim oluşturmak ve source.extension.vsixmanifest adlandırın. Visual Studio proje oluşturduğunda, VSIX paket Extension.VsixManifest bu dosyanın içeriği kopyalar.

## <a name="the-extensionvsixlangpack-file"></a>Extension.vsixlangpack dosyası

Extension.vsixlangpack dosya izleyen [VSIX Dil Paketi Şeması 2.0](../extensibility/vsix-language-pack-schema-2-0-reference.md). Bu şemayı sahip bir `PackageLanguagePackManifest`, hangi hemen ardından tarafından bir `Metadata` alt öğesi. Meta veri öğesi 6 alt öğelerini içerebilir `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, ve `Icon`. Bu alt öğeleri karşılık `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, ve `Icon` alt öğelerinin `Metadata` Extension.vsixmanifest dosyasının öğesi.

Vsixlangpack dosyası oluşturduğunuzda, ayarlamalısınız `Include in Vsix` özelliğine `true`. Aksi takdirde, yerelleştirilmiş yükleme metin göz ardı edilir.

### <a name="to-set-the-include-in-vsix-property"></a>INCLUDE VSIX özelliğini ayarlamak için

1. İçinde **Çözüm Gezgini**Extension.vsixlangpack dosyasını sağ tıklatın ve ardından **özellikleri**.

2.  Özellik kılavuzunda tıklatın **Include in VSIX**ve değerini ayarlama `true`.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, ilgili bölümleri İspanyolca için karşılık gelen Extension.vsixlangpack dosyası ile birlikte bir Extension.vsixmanifest dosyasının gösterir. Hedef bilgisayarın Visual Studio yerel ayar için İspanyolca olduğunda dil paketi değerleri bildirim değerleri değiştirin.

### <a name="code"></a>Kod

 [Extension.vsixmanifest]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest ...>
  <Metadata ...>
    <DisplayName>Family Tree</DisplayName>
    <Description>This extension places a custom treeview control in the toolbox that is optimized for handling family tree information.</Description>
    <MoreInfo>http://www.contoso.com/products/FamilyTree.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
  <Installation .../>
  <Dependencies .../>
  <Prerequisites .../>
  <Assets .../>
</PackageManifest>
```

 [Extension.vsixlangpack]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</DisplayName>
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
|[VSIX 2.0 LanguagePack şema başvurusu](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|VSIX Dil Paketi .vsix dağıtım dosyasının yerelleştirme bilgisi açıklar.|
|[VSIX paketi anatomisi](../extensibility/anatomy-of-a-vsix-package.md)|VSIX paketi içeriği ve yapısı açıklar.|
|[Yerelleştirme menü komutları](../extensibility/localizing-menu-commands.md)|Başka bir uzantı metin kaynaklarında yerelleştirme gösterilmektedir.|
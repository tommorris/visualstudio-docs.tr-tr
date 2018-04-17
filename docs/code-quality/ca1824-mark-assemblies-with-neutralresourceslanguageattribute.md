---
title: 'CA1824: Derlemeleri NeutralResourcesLanguageAttribute ile işaretleme | Microsoft Docs'
ms.date: 03/29/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3fdca585cf2c706dc83ecf9c1f7735c0d9d4f47e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Derlemeleri NeutralResourcesLanguageAttribute ile işaretleme

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep

Bir derlemeyi içeren bir **ResX**-kaynak temel ancak sahip olmadığı <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> uygulanmış.

## <a name="rule-description"></a>Kural açıklaması

<xref:System.Resources.NeutralResourcesLanguageAttribute> Özniteliği bir uygulamanın varsayılan kültürü Kaynak Yöneticisi'ni bildirir. Uygulamanın ana derlemede varsayılan kültürün kaynaklarının eklendiyse ve <xref:System.Resources.ResourceManager> varsayılan kültürü olarak aynı kültüre ait kaynakları alması gerekir <xref:System.Resources.ResourceManager> ana derlemesinde bulunan kaynaklara otomatik olarak kullanır için bir uydu derleme arama yerine. Bu normal derleme araştırma atlar, yükleme ve çalışma kümesi azaltabilir ilk kaynak için arama performansı geliştirir.

> [!TIP]
> Bkz: [paketleme ve dağıtma kaynakları](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) işlemi için <xref:System.Resources.ResourceManager> kaynak dosyaları için araştırma için kullanır.

## <a name="fix-violations"></a>İhlalleri Düzelt

Bu kural ihlal düzeltmek için öznitelik derlemeye eklemek ve bağımsız kültür kaynakları dili belirtin.

### <a name="to-specify-the-neutral-language-for-resources"></a>Kaynaklar için dilden belirtmek için

1. İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri**.

2. Seçin **uygulama** sekmesini tıklatın ve ardından **derleme bilgilerini**.

   > [!NOTE]
   > Projeniz .NET standart veya .NET Core projesiyse seçin **paket** sekmesi.

3. Dilden seçin **dilden** veya **derleme dilden** aşağı açılan liste.

4. Seçin **Tamam**.

## <a name="when-to-suppress-warnings"></a>Ne zaman uyarıları bastırma

Bu kural bir uyarıdan gizlemek için izin verilir. Ancak, başlangıç performansının düşmesine neden.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [Masaüstü uygulamalarında (.NET) kaynakları](/dotnet/framework/resources/)
- [CA1703 - kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701 - kaynak dize bileşik sözcüklerin doğru ortası](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
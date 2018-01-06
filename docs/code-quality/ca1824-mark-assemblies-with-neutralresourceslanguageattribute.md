---
title: "CA1824: Derlemeleri NeutralResourcesLanguageAttribute ile işaretleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6c9d4da3becaa6831f30a5cc6c72d1f0b3b70eea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
## <a name="rule-description"></a>Kural Tanımı  
 **NeutralResourcesLanguage** özniteliği bildirir **ResourceManager** için derlemeyi bağımsız kültür kaynakları görüntülemek için kullanılan dili. Bağımsız kaynaklar dili olarak aynı kültür kaynakları göründüğünde **ResourceManager** ana derlemesinde bulunan kaynaklara otomatik olarak kullanır. Geçerli kullanıcı arabirimi kültürü geçerli iş parçacığına sahip bir uydu derleme arama yerine bunu yapar. Bu ilk yüklediğiniz kaynak için arama performansını artırır ve çalışma kümenizi azaltabilir.  
  
## <a name="fixing-violations"></a>İhlallerini düzeltmek  
 Bu kural ihlal düzeltmek için öznitelik derlemeye eklemek ve bağımsız kültür kaynakları dili belirtin.  
  
## <a name="specifying-the-language"></a>Dil belirtme  
  
#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>Bağımsız kültür kaynak dili belirtmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri**.  
  
2.  Sol Gezinti Çubuğu'ndan seçin **uygulama**ve ardından **derleme bilgilerini**.  
  
3.  İçinde **derleme bilgilerini** iletişim kutusunda, dili seçin **nötr dil** aşağı açılan liste.  
  
4.  **Tamam**'ı tıklatın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan gizlemek için izin verilir. Ancak, başlangıç performansı düşebilir.
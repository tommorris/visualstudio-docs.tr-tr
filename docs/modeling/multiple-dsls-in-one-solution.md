---
title: "Bir çözümde birden çok DSL'ler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e668620-6217-4e87-aea7-e9036776c8e4
caps.latest.revision: "3"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: b55d1d5ec8e84c8d16681ffd0ac738291e1bc39d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="multiple-dsls-in-one-solution"></a>Bir Çözümde Birden Çok DSL
Böylece birlikte yüklenir tek bir çözümün bir parçası olarak birkaç DSL'ler paketleyebilirsiniz.  
  
 Birden çok DSL'ler tümleştirmek için birçok tekniği kullanabilirsiniz. Daha fazla bilgi için bkz: [modelleri Visual Studio Modelbus kullanarak tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md) ve [nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md) ve [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md).  
  
### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>Aynı çözüm içinde birden fazla DSL oluşturmak için  
  
1.  İki veya daha fazla DSL çözümleri ve VSIX projesi oluşturun ve tek bir çözüm için tüm projeleri ekleyin.  
  
    -   Yeni bir VSIX proje oluşturmak için: içinde **yeni proje** iletişim kutusunda **Visual C#**, **genişletilebilirlik**, **VSIX proje**.  
  
    -   İki veya daha fazla DSL çözümleri VSIX çözüm dizini oluşturun.  
  
         Her DSL için Visual Studio yeni bir örneğini açın. Yeni DSL oluşturun ve VSIX çözümü olarak aynı çözüm klasörü belirtin.  
  
         Farklı bir dosya adı uzantısı ile her DSL oluşturduğunuzdan emin olun.  
  
    -   Adları değiştirme **Dsl** ve **DslPackage** tüm farklı; böylece projeleri. Örneğin: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.  
  
    -   Her **DslPackage\*\source.extension.tt**, bu satırın doğru Dsl proje adına güncelleştirme:  
  
         `string dslProjectName = "Dsl2";`  
  
    -   VSIX çözümde Dsl * DslPackage ekleyip\* projeleri.  
  
         Kendi çözüm klasöründe her çifti yerleştirmek isteyebilirsiniz.  
  
2.  DSL'ler VSIX bildirimleri birleştirin:  
  
    1.  Açık *YourVsixProject***\source.extension.manifest**.  
  
    2.  Her DSL, seçin **İçerik Ekle** ekleyin:  
  
        -   `Dsl*`Proje olarak bir **MEF Bileşeni**  
  
        -   `DslPackage*`Proje olarak bir **MEF Bileşeni**  
  
        -   `DslPackage*`Proje olarak bir **VS Paketi**  
  
3.  Çözümü oluşturun.  
  
 Sonuçta elde edilen VSIX hem DSL'ler yükler. F5 kullanarak test veya dağıtmak *YourVsixProject***\bin\Debug\\\*.vsix**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Modelbus kullanarak modelleri tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md)
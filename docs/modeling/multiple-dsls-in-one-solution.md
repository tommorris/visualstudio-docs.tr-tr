---
title: "Bir çözümde birden çok DSL'ler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f3c024fc6be841f5329f133ece35ed0ef7517eb3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
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
  
    1.  Açık * YourVsixProject ***\source.extension.manifest**.  
  
    2.  Her DSL, seçin **İçerik Ekle** ekleyin:  
  
        -   `Dsl*`Proje olarak bir **MEF Bileşeni**  
  
        -   `DslPackage*`Proje olarak bir **MEF Bileşeni**  
  
        -   `DslPackage*`Proje olarak bir **VS Paketi**  
  
3.  Çözümü oluşturun.  
  
 Sonuçta elde edilen VSIX hem DSL'ler yükler. F5 kullanarak test veya dağıtmak * YourVsixProject ***\bin\Debug\\\*.vsix**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Modelbus kullanarak modelleri tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Kopyalama Davranışını Özelleştirme](../modeling/customizing-copy-behavior.md)
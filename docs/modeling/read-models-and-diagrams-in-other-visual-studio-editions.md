---
title: Diğer Visual Studio sürümlerindeki modelleri ve diyagramları okuma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 420a17dbac9e0a3bf10b4c92baa108067ad44949
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775587"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Diğer Visual Studio sürümlerindeki modelleri ve diyagramları okuma
Bir model oluşturmayı desteklemiyor Visual Studio sürümünde bir modeli açtığınızda, model salt okunur modunda açar. Bu modda, diyagram düzenini değiştirebilirsiniz, ancak modeli değiştiremezsiniz.

 Visual Studio'nun hangi sürümlerinin modeli oluşturulmasını desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Bir Model ve diyagramlarını erişim elde etme
 Bir bağımlılık diyagramı okumak için ilk modelleme projesini açmak için Visual Studio'yu kullanın ve ardından diyagramında açın.

 Bu nedenle, bir bağımlılık diyagramı okumak istiyorsanız, oluşturulduğu modelleme projesine erişim de olmalıdır. Projeden erişerek ya da bunu yapabilirsiniz [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)], ya da proje dosyalarının bir kopyasını alma.

> [!NOTE]
>  Bu kod için geçerli değildir haritaları ve .NET sınıf diyagramları koddan oluşturulan. Bu diyagramlar bir modelleme projesi bağımsız olarak görüntülenebilir.

 Bir bağımlılık diyagramı okumak için gereken dosyalar en düşük kümesini şu şekildedir:

-   İki dosyaları okumak için örneğin, istediğiniz diyagram için diyagram **MyDiagram.classdiagram ve MyDiagram.classdiagram.layout**.

    > [!NOTE]
    >  Bağımlılık diyagramları için adlı bir dosya da olmalıdır _Diyagramım_**. layerdiagram.suppressions**.

-   Modelleme Proje dosyası (**MyModel.modelproj**)

-   Kök model dosyası (**ModelDefinition\MyModel.uml**)

-   Şemada başvurulan herhangi bir paket için paket dosyaları (**ModelDefinition\MyPackage.uml**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Salt okunur modunda yaptığınız değişiklikler
 Bir model oluşturmayı desteklemiyor Visual Studio sürümünde bir model ve diyagramlarını açarsanız, modeli değiştiremezsiniz. Diğer bir deyişle, öğeleri ve ilişkileri diyagramlarda veya model Gezgini'nde görüntülenen değiştiremezsiniz. Ancak, diyagramların düzene bazı değişiklikler yapabilirsiniz:

-   Şekilleri ve bağlayıcıları diyagram üzerinde yeniden düzenleyin.

-   Şekilleri genişletme ve daraltma.

 Bu değişiklikleri kaydedebilirsiniz. Değişikliklerinizi diğer kullanıcılarına görünür hale getirmek isterseniz, en az güncelleştirilmiş gönderdiğiniz gerekir **.layout** dosyaları.

##  <a name="RelatedTopics"></a> İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)|Bir katman diyagramı, mevcut ya da önerilen bir mimari yapısı gösterilmektedir. Kodu yazıldığında otomatik olarak bir katman diyagramına karşı doğrulanabilir.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)
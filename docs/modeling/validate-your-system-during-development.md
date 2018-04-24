---
title: Geliştirme sırasında sisteminizi doğrulama
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d4ebc815f474f1b8a1c59c9736f9014ba02e523
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="validate-your-system-during-development"></a>Geliştirme sırasında sisteminizi doğrulama
Visual Studio yazılımınızı sisteminizin mimarisiyle ve kullanıcıların gereksinimleri ile tutarlı korunmasına yardımcı olabilirsiniz.

 Bu özelliklerin her biri, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Önemli görevleri
 Yazılım doğrulamak için aşağıdaki görevleri kullanın.

|**Görevler**|**İlgili Konular**|
|---------------|---------------------------|
|**Yazılım kullanıcıların gereksinimlerini karşıladığından emin olun**:<br /><br /> Sisteminiz ve bileşenlerinin testlerini düzenlemenize yardımcı olması için gereksinimleri ve mimari modelleri kullanabilirsiniz. Bu yöntem kullanıcılar ve diğer Paydaşlar için önemli olan gereksinimleri test ve gereksinimleri değiştiğinde testleri hızlı bir şekilde güncelleştirmenize yardımcı sağlamaya yardımcı olur.|-   [Model aracılığıyla test geliştirme](../modeling/develop-tests-from-a-model.md)|
|**Yazılımınızı sisteminizi hedeflenen tasarım ile tutarlı olmaya devam ettiğinden emin olun:**<br /><br /> Bağımlılık diyagramları uygulama bileşenleri arasında hedeflenen bağımlılıkları açıklar. Geliştirme sırasında koddaki gerçek bağımlılıkları hedeflenen tasarım ile uyumlu olduğunu doğrulayabilirsiniz.|-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Dış Kaynaklar

|**Kategori**|**Bağlantılar**|
|------------------|---------------|
|**Videolar**|![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug yedi: kod anlama ve Visual Studio 2010 ile sistem tasarımı](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: bağımlılık diyagramı kullanarak uygulama mimarisi oluşturma](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [MSDN nasıl yapmak ı serisi: nasıl bağımlılık diyagramları kullanarak kod doğrulamak için](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**Forumları**|-   [Visual Studio Görselleştirme ve Modelleme Araçları](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Görselleştirme ve modelleme SDK (DSL araçları)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Bloglar**|-   [Visual Studio ALM + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|
|**Teknik makaleler ve günlükleri**|[MSDN Mimari Merkezi](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Ayrıca Bkz.

- [Uygulamayı test etme](https://www.visualstudio.com/en-gb/docs/test/overview)
- [Kullanıcı gereksinimlerini modelleme](../modeling/model-user-requirements.md)
- [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

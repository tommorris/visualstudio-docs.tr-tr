---
title: Visual Studio'da birim test yöntemi saplamalar oluşturma
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ff06f81c641fdd3e2a62473d8ca162c3a019e97a
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302777"
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Birim testi yöntemi saplamalar ile birim testleri Oluştur komutu oluşturun.

Visual Studio **birim testleri oluşturma** komutu birim test yöntemi saplamalar oluşturma olanağı sağlar. Bu özellik, bir test projesi, test sınıfı ve içerdiği test yöntemi saplama kolay yapılandırmasını sağlar.

## <a name="availability-and-extensions"></a>Kullanılabilirlik ve uzantıları

**Birim testleri oluşturma** menü komutu:

* Community, Professional ve Enterprise sürümleri, Visual Studio 2015 kullanılabilir ve üzerinde desteklenir.

* .NET Framework hedefleyen yalnızca C# kod destekler.

* Genişletilebilir ve verme testleri mstest'i, mstest'i V2, NUnit, xUnit biçimini destekler.

## <a name="get-started"></a>Kullanmaya başlayın

Başlamak için bir yöntem, bir tür veya bir ad alanı test, kısayol menüsünü açın ve seçmek istediğiniz proje Kod düzenleyicisinde seçin **birim testleri oluşturma**. **Birim testleri oluşturma** iletişim kutusunu açar, burada yeni birim testleri oluşturma seçeneklerini seçilebilir.

![Create birim testleri komutu kullanma](media/createunittestcommand.png)

## <a name="setting-unit-test-traits"></a>Birim testi özellikleri ayarlama

Bu testleri test otomasyon işleminin bir parçası çalıştırmayı planlıyorsanız, başka bir test projesi (yukarıdaki iletişim ikinci seçeneği) oluşturulan test depolamayı düşünün ve nitelikler birim testi için test ayarı birimi. Bu, daha kolay dahil etmek veya sürekli tümleştirme veya sürekli dağıtım ardışık düzen parçası olarak bu belirli sınamalar hariç olanak sağlar. Nitelikler aşağıda gösterildiği gibi meta veriler için birim testi doğrudan ekleyerek ayarlanır.

![Birim testi özellikleri ayarlama](media/createunittest.png)

## <a name="using-third-party-unit-test-frameworks"></a>Üçüncü şahıs birim test çerçevelerini kullanarak

Visual Studio ile birim testleri için test framework kullanarak oluşturduğunuz kolayca olabilir. Diğer test çerçevelerini yüklemek için:

1. Seçin **Araçları** > **Uzantılar ve güncelleştirmeler**.
2. Genişletme **çevrimiçi** > **Visual Studio Market'te** > **Araçları**ve ardından **test**.

![Üçüncü taraf test çerçevelerini kullanarak](media/createunittestfx.png)

Test framework uzantıları Visual Studio Market'te bulunabilir kullanılabilir:

* [Test oluşturucuları için NUnit uzantısı](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [test oluşturucuları için xUnit.net uzantısı](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Bu özellik ne zaman kullanmalıyım?

Bu özelliği kullanmak birim testleri oluşturmak gereken zaman, ancak özellikle mevcut kodunuzu sınarken çok az kayıpla veya hiç test kapsamı ve hiçbir belge sahip. Diğer bir deyişle, söz konusu olduğunda sınırlı veya var olmayan kodu belirtimi. Etkili bir şekilde benzer bir yaklaşım uygular [akıllı birim testleri](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/19/introducing-smart-unit-tests.aspx) kod gözlemlenen davranışını niteleyen.

Ancak, bu özellik burada Geliştirici bazı kodlar yazarak başlar ve birim uzmanlık testi bootstrap kullanan durumunuz için eşit oranda geçerlidir. Kodlama nsg'lerin, geliştirici hızla (ile uygun test sınıfı ve uygun test projesi) saplama birim test yöntemi için belirli bir kod oluşturmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Birim testi "Oluşturmak ile birim testleri" yöntemi saplamalar oluşturma](https://blogs.msdn.microsoft.com/visualstudioalm/2015/03/06/creating-unit-test-method-stubs-with-create-unit-tests/)
- [Birim testi blog gönderileri](https://blogs.msdn.microsoft.com/devops/?s=unit+testing)

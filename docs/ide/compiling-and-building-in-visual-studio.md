---
title: Derleme ve Visual Studio'da derleme | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3ce6cf8cada1bbca4acad74b0df37ffa7d0c656a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="compiling-and-building-in-visual-studio"></a>Derleme ve Visual Studio'da derleme

Bir yapı çalıştıran derlemeler ve yürütülebilir uygulamalar kaynak kodunuz herhangi bir noktada bir geliştirme döngüsü sırasında oluşturur. Genel olarak, oluşturma işlemi Windows, ASP.NET, mobil uygulamaları ve diğerleri gibi birçok farklı proje türleri arasında çok benzer. Derleme işlemi ayrıca C#, Visual Basic, C++ ve F # gibi programlama dilleri arasında çok benzer. 

Kodunuzu genellikle oluşturarak, hızlı bir şekilde yanlış sözdizimi, yanlış yazılmış anahtar sözcükler gibi derleme zamanı hataları belirlemek ve uyuşmazlıkları yazın. Ayrıca hızlı bir şekilde algılamak ve sık derleme ve hata ayıklama kodu sürümlerini çalıştıran mantık hataları ve anlam hataları gibi çalışma zamanı hataları düzeltin.  

Aslında bir doğrulama uygulamanın kaynak kodu doğru sözdizimi içeriyor ve kitaplıkları, derlemeler ve diğer bileşenleri için tüm statik başvuruları çözümlendi buna başarılı bir yapıdır. Bu ardından uygun her ikisinde de çalışabilmesi için test edilebilir bir uygulamanın yürütülebilir üreten bir [ortamı hata ayıklama](../debugger/index.md) ve el ile hem de otomatikleştirilmiş testler için çeşitli [kod kalitesini doğrulamak](../test/improve-code-quality.md). Uygulamanın tam olarak test sonra müşterileriniz için dağıtmak için yayın sürümünü sonra derleyebilirsiniz. Bu işlem için bir giriş için bkz [izlenecek yol: uygulama oluşturma](../ide/walkthrough-building-an-application.md).  

Visual Studio ürün ailesi içinde bir uygulama oluşturmak için kullanabileceğiniz üç yöntem vardır: Visual Studio IDE MSBuild komut satırı araçları ve Team Foundation Build Visual Studio Team Services:
 
| Yöntemi oluşturma | Yararları | 
| --- |--- | --- |  
| IDE |-Derlemeleri hemen oluşturmak ve bunları bir hata ayıklayıcıda sınayın.<br />-Birden çok işlemcili derlemeleri C++ ve C# projeleri için çalıştırın.<br />-Yapı sistem farklı yönlerini özelleştirin. |
| MSBuild komut satırı| -Visual Studio yüklemeden projeleri oluşturun.<br />-Çalışma birden çok işlemcili için tüm proje türleri oluşturur.<br />-Yapı sistem çoğu alanlarının özelleştirin.|
| Team Foundation Derlemesi | -Yapı işleminizin sürekli tümleştirme/sürekli teslim ardışık bir parçası olarak otomatikleştirin.<br />-Her bir yapı ile otomatikleştirilmiş testleri uygulayın.<br />-Neredeyse sınırsız verebilir tabanlı kaynaklara yapı işlemleri için kullanın.<br />-Yapı iş akışı değiştirin ve son derece özelleştirilmiş görevleri gerçekleştirmek için yapı etkinlikleri oluşturun.|  

Bu bölümdeki belgelere Ayrıntılar IDE tabanlı derleme işleminin gider. Diğer yöntemler hakkında daha fazla bilgi için bkz: [MSBuild](../msbuild/msbuild.md) ve [sürekli tümleştirme ve dağıtım](https://www.visualstudio.com/docs/build/overview)sırasıyla.

## <a name="overview-of-building-from-the-ide"></a>IDE binanın genel bakış  

Bir proje oluşturduğunuzda, Visual Studio Proje ve proje içeren çözüm derleme yapılandırmaları varsayılan oluşturulur.  Bu yapılandırmaları nasıl çözümler ve projeler yerleşik dağıtılan ve tanımlayın. Proje yapılandırmaları özellikle hedef Platformu (örneğin, Windows veya Linux) için benzersiz ve yapı türü (örneğin, hata ayıklama veya yayın). İster ve kendi yapılandırmaları gerektiği gibi oluşturabilirsiniz ancak bu yapılandırmalar düzenleyebilirsiniz.

IDE içinden derleme ilk bir giriş için bkz: [izlenecek yol: uygulama oluşturma](walkthrough-building-an-application.md).  

Ardından, bkz: [yapı projeler ve çözümler ve Visual Studio Temizleme](building-and-cleaning-projects-and-solutions-in-visual-studio.md) farklı yönleri özelleştirmeleri hakkında bilgi edinmek için işlem yapabilirsiniz. Özelleştirmeleri içeren [çıktı dizinlerini değiştirme](how-to-change-the-build-output-directory.md), [özel belirtme derleme olaylarını](specifying-custom-build-events-in-visual-studio.md), [proje bağımlılıkları yönetme](how-to-create-and-remove-project-dependencies.md), [yapı günlüğünü yönetme dosyaları](how-to-view-save-and-configure-build-log-files.md), ve [Derleyici uyarılarını gizleme](how-to-suppress-compiler-warnings.md).

Buradan, çeşitli diğer görevleri gözden geçirebilirsiniz:
- [Derleme yapılandırmalarını anlama](understanding-build-configurations.md)
- [Derleme platformlarını anlama](understanding-build-platforms.md)
- [Proje ve çözüm özelliklerini yönetme](managing-project-and-solution-properties.md).  
- Derleme olayları belirtme [C#](how-to-specify-build-events-csharp.md) ve [Visual Basic](how-to-specify-build-events-visual-basic.md). 
- [Yapı seçeneklerini ayarlama](reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  

- [Web sitesi proje oluşturma (derleme)](http://msdn.microsoft.com/Library/a9cbb88c-8fff-4c67-848b-98fbfd823193)   

---
title: Projeleri derlemek için birden çok işlemci kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- multiple processors
- MSBuild, multiple processor systems
ms.assetid: 49fa36c9-8e14-44f5-8a2b-34146cf6807b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aff6d2ff6f509bca31283e2fbb04896f6e8adce9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="using-multiple-processors-to-build-projects"></a>Projeleri Derlemek için Birden Çok İşlemci Kullanma
MSBuild, birden çok işlemci veya birden çok çekirdekli işlemcilere sahip sistemler yararlanabilir. Ayrı oluşturma işlemi için kullanılabilir her işlemci oluşturulur. Sistem dört işlemci varsa, örneğin, ardından dört oluşturma işlemlerini oluşturulur. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Bu derlemeleri aynı anda işleyebilir ve bu nedenle genel derleme zamanında azalır. Ancak, paralel yapı oluşturma işlemlerini nasıl ortaya bazı değişiklikler tanıtır. Bu konu, bu değişiklikleri açıklamaktadır.  
  
## <a name="project-to-project-references"></a>Projeden Projeye Başvurular  
 Zaman [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] yalnızca bir kez başvuru yapıların paralel kullanırken proje proje (P2P) başvurusu olan bir projeyi derleme yapıları, karşılaştığı. İki proje aynı P2P başvuru varsa, her proje için başvuru yeniden değil. Bunun yerine, yapı altyapısı bağımlı her iki proje aynı P2P referansı döndürür. Aynı hedefe ilişkin oturumunda gelecekteki isteklerin aynı P2P başvuru sağlanır.  
  
## <a name="cycle-detection"></a>Döngü Algılama  
 Döngü algılama işlevleri, aynı, deki gibi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0 hariç, şimdi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] farklı bir zamanda veya yapı döngüsü algılama bildirebilirsiniz.  
  
## <a name="errors-and-exceptions-during-parallel-builds"></a>Paralel Yapılar Sırasında Hatalar ve Özel Durumlar  
 Paralel derlemelerde hataları ve özel durumları farklı zamanlarda paralel olmayan derlemede yapın ve bir projeyi derleme değil, diğer proje yapıları devam çok ortaya çıkabilir. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] başarısız bir paralel derleme herhangi bir proje yapı durdurmaz. Diğer projeler, bunlar da başarılı veya başarısız kadar oluşturmak devam edin. Ancak, varsa <xref:Microsoft.Build.Framework.IBuildEngine.ContinueOnError%2A> bir hata oluştuğunda dahi hiçbir derlemeleri durdurur sonra etkinleştirildi.  
  
## <a name="visual-c-project-vcproj-and-solution-sln-files"></a>Visual C++ Projesi (.vcproj) ve Çözüm (.sln) Dosyaları  
 Her ikisi de [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] için proje (.vcproj) ve çözüm (.sln) dosyalarını geçirilebilir [MSBuild görevi](../msbuild/msbuild-task.md). İçin [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri, VCWrapperProject çağrılır ve ardından dahili [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi oluşturulur. İçin [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] çözümler, bir SolutionWrapperProject oluşturulur ve ardından dahili [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi oluşturulur. Her iki durumda da, elde edilen proje davranılır diğer aynı [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi.  
  
## <a name="multi-process-execution"></a>Birden Çok İşlem Yürütme  
 Neredeyse tüm yapı ilgili etkinlikleri geçerli dizin yolu ile ilgili hataları önlemek için derleme işlemi boyunca sabit kalmasını gerektirir. Bu nedenle, farklı iş parçacıklarında üzerinde projeleri çalıştıramazsınız [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] oluşturulacak birden fazla dizine neden olacağından.  
  
 Bu sorunu önlemek ancak hala birden çok işlemcili derlemeleri etkinleştirmek için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] "işleminin kullandığı yalıtım." İşlem yalıtım kullanarak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] en fazla oluşturabilirsiniz `n` işlemleri, burada `n` sistemde kullanılabilir işlemci sayısına eşittir. Örneğin, varsa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] derlemeleri işlemleri yalnızca iki yapı sonra iki işlemciye sahip bir sistemde bir çözüm oluşturulur. Bu işlemler Çözümdeki tüm projeleri derlemek için yeniden kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)   
 [Görevler](../msbuild/msbuild-tasks.md)
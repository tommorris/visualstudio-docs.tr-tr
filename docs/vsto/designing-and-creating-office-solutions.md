---
title: "Tasarlama ve Office çözümleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], creating
- Office development in Visual Studio, creating solutions
- solutions [Office development in Visual Studio], creating
- Office project types in Visual Studio
ms.assetid: 53c32c61-3d3a-4427-a5a7-f9c2c8f1de02
caps.latest.revision: "103"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 02f5d5cf2d726755cce4b3de2dcd74a5dad18db6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="designing-and-creating-office-solutions"></a>Office Çözümleri Tasarlama ve Oluşturma
  Visual Studio birkaç farklı türde Office çözümleri oluşturmak için kullanabileceğiniz proje şablonları sağlar. Bu bölümde belgelerin proje şablonlarını açıklar ve Office projeleri oluşturma hakkında yönergeler sağlar. Projenizi oluşturduktan sonra kod ve kullanıcı arabirimi özelleştirmelerini uygulamak hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirme](../vsto/developing-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="creating-office-projects"></a>Office projeleri oluşturma  
 Başlamadan önce gereksinimlerinizi belirlemek ve en uygun çözümü türünü bulur. Örneğin, Office çözümünüzün uygulama kullanılır, her zaman bir VSTO eklenti en iyi sığar gereksinimlerinizi çalıştırmanız gerekir. Kod ile tek bir belgenin tümleşiktir varsa, bir belge düzeyi özelleştirme oluşturun. Bu proje türleri, Visual Studio Proje şablonları kullanılabilir. Visual Studio ile birlikte Office proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md). Office projeleri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Office projelerinde özellikler ve diğer Visual Studio Proje türleri farklıdır proje öğeleri vardır. Örneğin, bir belge düzeyi projesi oluşturduğunuzda, belge veya projenizdeki çalışma kitabının açılabilir ve Visual Studio içinde düzenlenebilir. Daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="choosing-a-net-framework-version"></a>.NET Framework sürümünü seçme  
 Gereksinimlerinize en uygun proje türünü seçtikten sonra geliştirme sürecinizde kullanmak için .NET Framework'ün hangi sürümünün seçebilirsiniz. Office projelerinde aşağıdaki .NET Framework sürümlerini hedefleyebilirsiniz:  
  
-   [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]  
  
-   [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]  
  
-   [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
  
 Projeniz için seçtiğiniz .NET Framework sürümünü çalıştırmak, çözümünüz için son kullanıcı bilgisayarlarında gereklidir. Örneğin, projenizin hedeflediği [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] son kullanıcı bilgisayarlarında gereklidir. .NET Framework 3.5 son kullanıcı bilgisayarlarında yüklü yalnızca bu örnekte, çözümünüzü çalışmaz.  
  
 .NET Framework 3.5 hedefleyen bir VSTO eklenti projesi geçirirseniz, Visual Studio projenize hedef Framework'ü değişiklikleri [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya üstü yüklü olan Office sürümüne bağlı olarak.  
  
 Ancak, Visual Studio hedef Framework'ü değişiklikler sonra bazı özellikleri kullanıyorsa, bazı projenizdeki kodu değiştirmeniz gerekebilir. Hedef Framework'ü değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md). Projenizde yapmanız gerekebilen değişiklikler hakkında daha fazla bilgi için bkz: [geçirme Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
 Visual Studio, projenizin hedef .NET Framework değiştirir ve çözümünüzü dağıtmak için ClickOnce kullanarak, .NET Framework'ün karşılık gelen sürümü de seçtiğinizden emin olun **Önkoşullar** iletişim kutusu. Projeniz için hedef Framework'ü değiştirdiğinizde, bu seçimi otomatik olarak değişmez. Daha fazla bilgi için bkz: [nasıl yapılır: Office çözümlerini çalıştırmak için yükleme önkoşulları son kullanıcı bilgisayarlarında](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
> [!NOTE]  
>  .NET Framework 3.5 veya önceki kullanarak oluşturduğunuz Office projelerinde hedefleyemez [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]. Kullanarak oluşturduğunuz office projeleri [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] sürümünde ilk yapılan özellikleri gerektirir[!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]  
  
### <a name="understanding-when-the-office-pias-are-required-on-end-user-computers"></a>Son kullanıcı bilgisayarlarında Office PIA gerektiğinde anlama  
 Varsayılan olarak, Office birincil birlikte çalışma derlemeleri (PIA) son kullanıcı bilgisayarlarında yüklü gerekmez **birlikte çalışma türlerini katıştır** projesinde her Office PIA başvuru özelliği ayarlanmış **doğru**, hangi varsayılan değerdir. Bu senaryoda, projeyi derlerken çözümünüz tarafından kullanılan PIA türleri için tür bilgisi çözüm derlemeye katıştırılır. Çalışma zamanında gömülü tür bilgileri yerine PIA Office uygulamasının COM tabanlı nesne modelini çağırmak için kullanılır. PIA türlerinden çözümünüze nasıl katıştırılmış hakkında daha fazla bilgi için bkz: [tür Eşdeğerliği ve katıştırılmış birlikte çalışma türlerini](/dotnet/framework/interop/type-equivalence-and-embedded-interop-types).  
  
 Varsa **birlikte çalışma türlerini katıştır** projesinde her Office PIA başvuru özelliği ayarlanmış **yanlış**, Office PIA yüklenmeli ve genel derleme önbelleğinde her son kullanıcı bilgisayarda kayıtlı, Çözüm çalışır. Çoğu durumda, PIA Office ile varsayılan olarak yüklenir, ancak çözümünüz için bir önkoşul olarak yeniden dağıtılabilir PIA da içerebilir. Daha fazla bilgi için bkz: [dağıtım için Office çözümü önkoşulları](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e).  
  
### <a name="understanding-the-client-profile"></a>İstemci profilini anlama  
 .NET Framework istemci profili tam .NET Framework'ün bir alt kümesidir. .NET Framework istemci profili, .NET Framework'teki yalnızca istemci özelliklerini kullanmanız gerekir ve Office çözümünüz için en hızlı olası dağıtım deneyimi sağlamak istiyorsanız hedefleyebilirsiniz. Daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).  
  
 ' İ hedefleyen Office proje oluşturduğunuzda [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)] varsayılan olarak hedeflenir. İçin tam geliştirmek istiyorsanız [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], Proje oluşturulduktan sonra bu seçenek ayarlamanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
## <a name="creating-solutions-for-the-64-bit-edition-of-microsoft-office"></a>Çözümleri Microsoft Office'in 64-bit sürümü için oluşturma  
 Microsoft Office 64-bit ve 32-bit sürümlerinde kullanılabilir. Her iki sürümde de çalıştırabilirsiniz Office çözümleri oluşturmak için projenizin platform hedefi ayarları ayarlanmalıdır **herhangi bir CPU**. Office projeleri için varsayılan değer budur. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
 Ayrı 64-bit ve 32-bit sürümü vardır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft Office 64-bit ve 32 bit sürümleri tarafından kullanılır. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="assemblies-in-office-solutions"></a>Office çözümlerinde derlemeler  
 Visual Studio'da Office geliştirme araçlarını kullanarak bir Office proje oluşturduğunuzda, yazdığınız kodu sonunda bir derlemeye derlenmiştir. Derleme genellikle paylaşılan bir sunucu veya istemci bilgisayarda bir dizine dağıtılır.  
  
 Office çözümlerinde derlemeler bir Office uygulaması tarafından yüklenir. Bütünleştirilmiş kod, derleme yüklendikten sonra bir kullanıcı bir menü öğesini tıkladığında uygulamada, örneğin, başlatılan olaylara yanıt verebilir. Bütünleştirilmiş kod ayrıca nesne modelini çağırıp uygulamayı genişletebilir çağırın ve sınıflarda birini kullanabilirsiniz [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)]. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
 Office çözümleri derleme tanımlamak için dağıtım bildirimleri ve uygulama bildirimlerini kullanın. Uygulama bulmak, bağlantı ve doğru derleme çalıştırmak bildirimler derlemenin adı, sürüm ve konumu hakkında bilgi içerir. Daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini Office çözümlerinde](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
 Belge düzeyi projelerine bütünleştirilmiş yanı sıra bir belge içerir. Belge uygulamanın ön ucu olarak görev yapar ve tüm kullanıcı etkileşimi gerçekleştiği. Her bir belgenin ilişkili yalnızca bir ana proje derlemesi olabilir; Ancak, birden çok belge aynı derlemeye işaret edebilir.  
  
 Belge düzeyi projelerine derlemelerde belgede gömülü değildir. Bunun yerine, başka bir yerde depolanır ve belgenin uygulama bildirimi tarafından tanımlanır.  
  
## <a name="security-considerations-for-assemblies"></a>Derlemeler için güvenlik konuları  
 Office çözümünü bir bilgisayarda çalıştırmak çözüm tarafından kullanılan derlemeler çalıştırmak için güvenilir olması gerekir. Güvenlik hakkında daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
 Çözüm derleme ve projenizin çıktı klasöründe bulunan tüm başvurulan derlemeler varsayılan olarak, projeyi derlerken geliştirme bilgisayarınızda çalıştırmak için güvenilir. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
 Güvenlik nedenleriyle, yerel bilgisayarınızda proje oluşturmak en iyi yerine geliştirme üzerinde paylaşılan bir konum. Daha fazla bilgi için bkz: [işbirlikçi geliştirme, Office çözümleri](../vsto/collaborative-development-of-office-solutions.md).  
  
## <a name="referenced-assemblies"></a>Başvurulmuş Derlemeler  
 Derleme projenin başvurularında listelenen diğer derlemelerden başvuruda bulunabilir. Ancak, bir belge düzeyi projesi derleme başka bir belge düzeyi proje derlemesi başvuramaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md)   
 [Office projelerinde Özellikler](../vsto/properties-in-office-projects.md)   
 [Çözümleri Microsoft Office'in farklı sürümlerinde çalıştırma](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)   
 [Nasıl yapılır: birincil birlikte çalışma derlemeleriyle Office uygulamalarını](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Uygulama ve dağıtım bildirimlerini Office çözümleri](../vsto/application-and-deployment-manifests-in-office-solutions.md)   
 [Nasıl yapılır: Office çözümü için yapılandırma bilgilerini ayarlama](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md)   
 [Visual Studio içinde Office işlevselliğini kullanma](../vsto/using-office-functionality-inside-of-visual-studio.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office programlarındaki ortak görevler](../vsto/common-tasks-in-office-programming.md)   
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  
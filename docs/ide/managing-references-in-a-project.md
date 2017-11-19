---
title: "Bir projedeki başvuruları yönetme | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.ProjectPropertiesReferencePaths
- cs.ProjectPropertiesReferencePaths
helpviewer_keywords:
- Visual C# projects, references
- referencing objects, project references
- external component references
- referencing namespaces
- Visual Basic projects, references
- referencing components, external components
- Web references, types of project references
- namespaces [Visual Studio], referencing
- COM components, referencing
- objects [Visual Studio], referencing
ms.assetid: 05d1c51b-44f3-4973-8a11-6c919b08ad62
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4145dda187e726096e2137d2a5fdc0455b6131e2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-references-in-a-project"></a>Bir projedeki başvuruları yönetme
Dış bileşen karşı kod yazın veya hizmeti bağlı önce projenize önce bir başvuru içermelidir. Aslında Visual Studio bileşen veya hizmet bulmak gerekli bilgileri içeren bir proje dosyasındaki bir giriş başvurudur.  

 Bir başvuru eklemek için Çözüm Gezgini'nde başvurular düğümünü sağ tıklatın ve seçin **Başvuru Ekle**. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md).  

 ![Visual C# 43; &#43;içinde bir başvuru ekleyin; ] (../ide/media/vs2015_cpp_add_reference.png "vs2015_cpp_add_reference")  

 Aşağıdaki bileşenler ve hizmetlerle türlerini başvuru yapabilirsiniz:    

-   .NET framework sınıf kitaplıkları veya derlemeler  

-   UWP uygulamaları

-   COM bileşenleri  

-   Diğer derlemeler veya aynı çözümdeki projelerin sınıf kitaplıkları  

-   XML Web hizmetleri  

## <a name="uwp-app-references"></a>UWP uygulama başvuruları  

### <a name="project-references"></a>Proje başvuruları  
 Evrensel Windows Platformu (UWP) projeleri bu projeleri Windows 10'da kullanım dışı API'ları kullanmayın sağlanan başvuruları diğer UWP projeleri veya Windows 8.1 projeleri veya ikili dosyaları, oluşturabilirsiniz. Daha fazla bilgi için bkz: [UWP'ye Windows çalışma zamanı 8'den Taşı](https://docs.microsoft.com/en-us/windows/uwp/porting/w8x-to-uwp-root).  

 Windows 10 için Windows 8.1 projeleri yeniden hedefleyin isterseniz bkz [bağlantı noktası, geçirme ve Visual Studio projelerini yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)  

### <a name="extension-sdk-references"></a>Uzantı SDK başvurular  
 Visual Basic, C#, C++ ve JavaScript Evrensel Windows Platformu (UWP) uygulamaları uzantısı SDK'ları hedefleyen başvuru [!INCLUDE[win81](../debugger/includes/win81_md.md)], bu uzantı SDK'ları Windows 10'da kullanım dışı API'ları kullanmayın sürece. Lütfen olup, Microsoft Store projeler tarafından başvurulabilir çıkışı hedefleyen UWP bulmak için uzantı SDK satıcı sitesini denetleyin.  

 Karar verirseniz, uygulamanız tarafından başvurulan uzantısı SDK desteklenmiyor sonra aşağıdaki adımları gerçekleştirmeniz gerekir:  

1.  Hataya neden olan projesinin adı arayın. Projenizi hedefleme platform proje adının yanında parantez içinde belirtilir. Örneğin, **MyProjectName (Windows 8.1)** projenizi anlamına **MyProjectName** platform sürümü hedefleme [!INCLUDE[win81](../debugger/includes/win81_md.md)].  

2.  Desteklenmeyen uzantı SDK'sı sahibi satıcı sitesine gidin ve projenizin hedefleme platform sürümü ile uyumlu olan bağımlılıkları olan uzantı SDK sürümünü yükleyin.  

    > [!NOTE]
    >  Bir uzantı SDK bağımlılıkları diğer uzantısı SDK olup bulmak için bir yoldur Visual Studio'yu yeniden başlatın, yeni bir C# UWP uygulaması projesi oluşturduğunuzda, projeye sağ tıklayın ve seçmek için **Başvuru Ekle**gidin **Windows**  sekmesine gidin **uzantıları** alt sekmesinde uzantısı SDK'yı seçin ve sağ bölmede bakmak **başvuru Yöneticisi**. Bağımlılıkları varsa, bunlar var. listelenir.  

    > [!IMPORTANT]
    >  Windows 10 projenizi hedefleme ve uzantısı önceki adımda yüklenen SDK'sı Microsoft Visual C++ çalışma zamanı paketi üzerinde bir bağımlılık varsa sürümü Microsoft Visual C++ çalışma zamanı Windows 10 ile uyumlu olan paketi v14.0 ve yüklü Visual Studio ile.  

3.  Önceki adımda yüklediğiniz uzantısı SDK diğer uzantısı SDK bağımlılıklarına sahipse, bağımlılıkları sahibi satıcıları siteleri için gidin ve platform sürümü ile uyumlu Bu bağımlılıklar sürümlerini yüklemek için Proje hedefleme.  

4.  Visual Studio'yu yeniden başlatın ve uygulamanızı açın.  

5.  Sağ **başvuruları** hata neden oldu ve proje düğümüne **Başvuru Ekle**.  

6.  Tıklatın **Windows** sekmesini ve ardından **uzantıları** alt sekmesinde sonra eski uzantısı SDK'ları için onay kutusunun işaretini kaldırın ve yeni uzantı SDK'ları için onay kutularını denetleyin. **Tamam**'ı tıklatın.  

## <a name="adding-a-reference-at-design-time"></a>Tasarım zamanında bir başvuru ekleme  
 Projenizde, bir derlemesine başvuru yaptığınızda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] derleme aşağıdaki konumlarda arar:  

-   Geçerli proje dizini. (Bu derlemeler kullanarak bulabilirsiniz **Gözat** sekmesi.)  

-   Diğer aynı çözüme proje dizinlerde. (Bu derlemeler bulabilirsiniz **projeleri** sekmesi.)  

> [!NOTE]
>  Tüm projeleri mscorlib dolaylı bir başvuru içeriyor. Visual Basic projeleri için dolaylı bir başvuru içeren `Microsoft.VisualBasic`.  
>   
>  Visual Studio'daki tüm projeleri dolaylı bir başvuru içeren `System.Core`olsa bile `System.Core` başvuruları listesinden kaldırılır.  

## <a name="references-to-shared-components-at-run-time"></a>Çalışma zamanında başvurular paylaşılan bileşenleri  
 Çalışma zamanında bileşenleri projenin çıkış yolu veya genel derleme önbelleği (GAC) içinde olmalıdır. Proje şu konumlardan birinde olmayan bir nesneye başvuru içeriyorsa, projeyi derlerken çıkış yolu projenin referansı kopyalamanız gerekir. <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> Özelliği, bu kopya yapılması sahip olup olmadığını belirtir. Değer ise **doğru**, projeyi derlerken başvuru proje dizinine kopyalanır. Değer ise **yanlış**, başvuru kopyalanmaz.  

 GAC içinde kayıtlı bir özel bileşenine bir başvuru içeren bir uygulamayı dağıtırsanız, bileşen uygulama ile bakılmaksızın dağıtılmaz <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> ayarı. Önceki sürümlerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ayarladığınız <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> derleme dağıtıldı emin olmak için bir başvuru özelliği. Şimdi, \Bin klasörüne el ile derleme eklemeniz gerekir. Bu, size tanıdık olmayan özel kod yayımlama riskini azaltma scrutiny altındaki tüm özel kod koyar.  

 Varsayılan olarak, <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> özelliği ayarlanmış **False** derleme veya bileşeni Genel Derleme Önbelleği'ya bir çerçeve bileşeni ise. Değer kümesine Aksi halde, **doğru**. Proje Proje başvuruları her zaman ayarlanır **doğru**.  

## <a name="referencing-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Başvuran bir proje veya farklı bir .NET Framework sürümünü hedefler derleme  
 Projeleri veya farklı bir .NET Framework sürümünü hedef derlemeleri başvuruda bulunan uygulamaları oluşturabilirsiniz. Örneğin, bir uygulama hedefleyen oluşturabilirsiniz [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)] hedefleyen bir derlemeyi başvuran [!INCLUDE[dnprdnext](../ide/includes/dnprdnext_md.md)]. Önceki bir sürümünü hedefleyen bir proje oluşturduğunuzda [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], başvuru bu projede bir proje veya derleme hedefleyen ayarlayamazsınız [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)] veya .NET Framework sürüm 4.  

 Daha fazla bilgi için bkz: [belirli bir .NET Framework sürümü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md).  

## <a name="project-to-project-references"></a>Proje Proje başvuruları  
 Proje Proje başvuruları derlemeleri içeren projelere başvurular; yine de uygun istiyor musunuz? bunları kullanarak oluşturduğunuz **proje** sekmesi. Visual Studio derleme yolu projeye verildiğinde bulabilirsiniz.  

 Bir derlemeyi üreten bir proje sahip olduğunuzda, proje başvurusu ve dosya başvurusu (aşağıya bakın) kullanmamanız gerekir. Proje proje başvurusu avantajlarından yapı sistem projeler arasında bir bağımlılık oluşturmasıdır. Başvuru proje oluşturulan en son ne zaman beri değişmişse bağımlı proje oluşturulacak. Dosya başvurusu, başvuru proje bağımlı proje oluşturmadan oluşturmak mümkün müdür ve başvuru geçersiz hale gelebilir derleme bağımlılığına oluşturmaz. (Diğer bir deyişle, proje önceden oluşturulmuş bir projenin sürümü başvurabilir.) Bu mümkün olmayan bin dizininde, gerekli tek bir DLL birçok sürümü neden olabilir. Bu çakışma oluştuğunda bir ileti gibi görürsünüz "Uyarı: 'dosya' başvuru üzerine yazacağından 'proje' projesindeki ' dosya' bağımlılığı çalıştırma dizinine kopyalanamıyor". Daha fazla bilgi için bkz: [bozuk başvuruları sorun giderme](../ide/troubleshooting-broken-references.md) ve [nasıl yapılır: oluşturun ve proje bağımlılıkları kaldırın](../ide/how-to-create-and-remove-project-dependencies.md).  

> [!NOTE]
>  Bir dosya başvurusu proje proje başvurusu yerine hedef bir proje .NET Framework sürüm 4.5 sürümüdür ve diğer projenin hedef sürüm 2, 3, 3.5 veya 4.0 sürümünü ise oluşturulur.  

## <a name="file-references"></a>Dosya başvuruları  
 Dosya başvuruları Visual Studio projesi bağlamı dışında derlemeleri doğrudan başvurusudur; bunları kullanarak oluşturduğunuz **Gözat** sekmesinde **başvuru Yöneticisi**. Yalnızca bir derlemeyi ya da bileşen varsa ve çıkış olarak oluşturur proje yok dosya başvurusu kullanın.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Bozuk başvurularda sorun giderme](../ide/troubleshooting-broken-references.md)   
 [Nasıl yapılır: başvuru ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md)

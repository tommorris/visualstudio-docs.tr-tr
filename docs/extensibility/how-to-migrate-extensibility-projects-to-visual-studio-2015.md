---
title: 'Nasıl yapılır: Visual Studio 2015 genişletilebilirlik projeleri geçirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, upgrading
ms.assetid: 22491cdc-8f04-4e1c-8eb4-ff33798ec792
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5adad311c1696d958902d9ad33ed1d1872606458
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2015"></a>Nasıl yapılır: Visual Studio 2015 genişletilebilirlik projeleri geçirme
Uzantınızı yükseltme bırakılır.  
  
> [!IMPORTANT]
>  Uzantı çözümünüz için Visual Studio'nun önceki bir sürümünü sürümünü korumak istiyorsanız, yükseltmeden önce bir kopya yapmak emin olun. Yükseltilmiş sürüm önceki durumuna geri döndürmek zor olabilir.  
  
#### <a name="to-upgrade-an-extensibility-solution"></a>Genişletilebilirlik çözümünü yükseltmek için  
  
1.  Kopyalama kullanarak istediğiniz yükseltme, yeni sürümde açın. Yükseltme ters çevrilebilir değil göre artırılmıştır.  
  
2.  Yükseltme tamamlandıktan sonra dış program yolu devenv.exe yeni sürüm olarak değiştirin. Proje düğümüne sağ tıklayın **Çözüm Gezgini**, ardından **özellikleri**. İçinde **hata ayıklama** sekmesinde, textbox tarafından Bul **başlangıç dış program** ve bu gibi görünmelidir Visual Studio 2015 yoluna devenv.exe yolunu değiştirin:  
  
     **%ProgramFiles%\Microsoft visual Studio 14.0\Common7\IDE\devenv.exe**  
  
3.  Microsoft.VisualStudio.Shell.14.0.dll bir başvuru ekleyin. (Proje düğümüne sağ tıklayın **Çözüm Gezgini** ve ardından **ekleme / Reference**. Select **uzantıları** sekmesini ve ardından denetleyin **Microsoft.VisualStudio.Shell.14.0**.)  
  
4.  Çözümü oluşturun. Yerleşik dosyaları dağıtılır:  
  
     **%LocalAppData%\Microsoft\VisualStudio.14.0Exp\Extensions\\< yazar adı\>\\< proje adı\>\\< proje sürüm\>\\**.  
  
#### <a name="to-update-an-extensibility-project-to-nuget-vs-sdk-reference-assemblies"></a>Genişletilebilirlik projesi için NuGet VS SDK başvuru derlemeleri güncelleştirmek için  
  
1.  Projenizi gereken VS SDK başvuru derlemeleri belirler.  İçinde **Çözüm Gezgini**, projenin genişletin **başvuruları** düğümü ve proje başvuruları listesini gözden geçirin.  VS SDK başvuruları derlemeleri öneki olacaktır **Microsoft.VisualStudio** adında (örneğin: Microsoft.VisualStudio.Shell.14.0).  
  
2.  Bunları seçerek VS SDK başvuru derlemeleri projeden kaldırmak için sağ tıklayın ve **kaldırmak**.  
  
3.  VS SDK başvuru derlemeleri NuGet sürümleri ekleyin.  Hala while **Solution Explorer başvuruları** düğümü, açık **NuGet paketlerini Yönet...**  iletişim.  Bu iletişim kutusu hakkında daha fazla bilgi edinmek istiyorsanız, bkz: [Paket Yöneticisi kullanıcı Arabirimi](/NuGet/Tools/Package-Manager-UI). VS SDK başvuru derlemeleri üzerinde yayımlanan [nuget.org](http://www.nuget.org) tarafından [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility).  
  
4.  Kullanarak **nuget.org** olarak, **paket kaynağı**, istenen referans derlemesini eşleşen NuGet paket adı arayın (örneğin: Microsoft.VisualStudio.Shell.14.0) ve bunu yüklemek, Proje.  NuGet ilk derlemenin bağımlılıklarını karşılamak için birden fazla başvuru derlemeleri ekleyebilir.  
  
     Tercih ederseniz, tüm VS SDK başvuru derlemeleri aynı anda VS SDK yükleyerek ekleyebileceğiniz [Meta paket](http://www.nuget.org/packages/VSSDK_Reference_Assemblies).  
  
5.  Ayrıca, VS SDK derleme araçlarını NuGet sürümünü kullanmaya geçiş yapabilirsiniz. Bu NuGet paketi [Microsoft.VSSDK.BuildTools](http://www.nuget.org/packages/Microsoft.VSSDK.BuildTools) ve bir kez eklenir projeniz gerekli araçlar içerir ve hedef dosyaları genişletilebilirlik projenizi bir bilgisayarda yüklü VS SDK oluşturmanızı sağlar.  
  
> [!NOTE]
>  Olmayan NuGet başvuru derlemeler ve Araçlar kullanmak için mevcut genişletilebilirlik projelerinizi güncelleştirmeniz gerekiyor.  Bunlar başvuru derlemeleri ve VS SDK ile birlikte yüklenen araçları kullanarak oluşturmaya devam edebilirsiniz.
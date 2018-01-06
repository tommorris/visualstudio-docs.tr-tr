---
title: "Visual Studio Shell yalıtılmış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], shell-based applications, isolated mode
- Visual Studio shell, isolated mode
- isolated shell-based applications [Visual Studio]
- Visual Studio shell, shell-based applications, isolated mode
- Shell [Visual Studio], isolated mode
ms.assetid: d2620e71-be9e-44c9-b5b7-03a4c8d9cf0b
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e80b947b2d4d20692e0abceae0ffa36e64f2b0df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-isolated-shell"></a>Visual Studio yalıtılmış Kabuk
Visual Studio yalıtılmış Kabuk yan yana çalıştırabileceğiniz bağımsız uygulamalar oluşturmanıza olanak tanıyan diğer Visual Studio sürümleri ile. Visual Studio hizmetleri kullanan ancak özelleştirilmiş bir görünümünü de özel araçlar öncelikle barındırmak için kullanılan ve marka. Visual Studio özellikleri ve menü komut gruplarını, kolayca açma ve kapatma açılabilir. Uygulama başlıkları, uygulama simgeleri ve başlangıç ekranında tamamen özelleştirilebilir. Özelleştirilebilir özelliklerin listesi için bkz: [yalıtılmış Kabuk özelleştirme](customizing-the-isolated-shell.md).  
  
 Yalıtılmış Kabuk projesi ile çalışmak için Visual Studio SDK'yı yüklemeniz gerekir. Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../installing-the-visual-studio-sdk.md).  
  
 Yalıtılmış Kabuk uygulama oluşturmak için Visual Studio Shell yalıtılmış bir proje başlatın. Bu proje geliştirmek ve kendi yalıtılmış Kabuk uygulamanızı test etmek için gereken her şeyi içerir. Uygulamanızı dağıtır Kurulum programı yazmak hazır olduğunuzda, yalıtılmış Kabuk yeniden dağıtılabilir paketi almalısınız [Microsoft Visual Studio Kabuğu (Yalýtýlmýþ) yeniden dağıtılabilir paketi](http://go.microsoft.com/fwlink/?LinkId=616022).  
  
> [!NOTE]
>  Yalıtılmış Kabuk yeniden dağıtılabilir paketi erişebilmeniz için önce bir kısa müşteri araştırması doldurmak için istenir.  Out anket doldurduktan sonra yeniden dağıtılabilir paketi yükleme bağlantıları ile Visual Studio bağlanmak sayfasına yönlendirilirsiniz.  Visual Studio Connect sitesindeki altında için sonraki ziyaretlerinizde indirme bağlantıları bulabilirsiniz **programları &#124; VISUAL STUDIO 2015 TÜMLEŞİK ve YALITILMIŞ KABUK** sekmesi.  
  
> [!NOTE]
>  Yalıtılmış kabuk tabanlı uygulama dağıtma hakkında daha fazla bilgi için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="working-with-the-isolated-shell"></a>Yalıtılmış Kabuk ile çalışma  
 Visual Studio yalıtılmış Kabuk uygulamanızı Visual Studio Hizmetleri tam erişimi olduğundan ve özel özelleştirme ve markalama destekler. Yalıtılmış Kabuk uygulamanızı özelleştirebilirsiniz birkaç yolu vardır:  
  
-   Yalnızca bunları herhangi diğer Visual Studio Uzantısı'nda kullanırsınız gibi yalıtılmış Kabuk uygulama genişletmek için VSPackages ve Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümleri kullanabilirsiniz. Daha fazla bilgi için bkz: [yalıtılmış Kabuk genişletme](extending-the-isolated-shell.md).  
  
-   Visual Studio özellikleri ve menü komut gruplarını kullanılabilir veya kullanılamaz hale getirmek için uygulamanın kullanıcı arabirimini (UI) projesindeki .vsct dosyasını güncelleştirin.  
  
-   Kaldırmak için **seçenekleri** sayfaları veya Visual Studio Kabuğu bileşenlerle uygulamadan güncelleştirme uygulamanın .pkgundef dosyası.  
  
-   Görünümü diğer yönlerini veya kabuk davranışını değiştirmek için uygulamanın .pkgdef dosyasını güncelleştirin.  
  
-   Uygulama başlatıldığında Kabuk bazı yönlerini de belirtilebilir. Bunu yapmak için başlangıç giriş noktasını appenvstub.dll çağrısında parametreleri güncelleştirin.  
  
 Özelleştirebileceğiniz farklı öğeler hakkında daha fazla bilgi için bkz: [öğeleri yalıtılmış Kabuk](elements-of-the-isolated-shell.md).  
  
## <a name="standard-features-of-the-isolated-shell"></a>Yalıtılmış Kabuk standart özellikler  
 Aşağıdaki özellikler için Visual Studio'nin tüm sürümlerinde standart.  
  
|Özellik kategorisi|Özellik|  
|----------------------|-------------|  
|IDE özellikleri|İçeri/dışarı aktarma ayarları<br /><br /> Araç kutusu denetim yükleyici<br /><br /> Görev listesi & hata listesi<br /><br /> Çıktı Penceresi<br /><br /> Başlangıç Sayfası<br /><br /> Özellikler Penceresi<br /><br /> Araç Kutusu<br /><br /> Çözüm Gezgini<br /><br /> Yer işareti penceresi<br /><br /> Sınıf Görünümü<br /><br /> Nesne Tarayıcısı<br /><br /> Komut Penceresi<br /><br /> Belge Anahattı<br /><br /> Kaynak Görünümü<br /><br /> Dış Aracı<br /><br /> Windows Communication Foundation (WCF) hizmet Başvurusu Ekle<br /><br /> Dil tümleşik sorgu (LINQ) desteği|  
|Düzenleyici/Tasarımcısı|Kod Tarama Araçları (Birleşik bulma, kaynak tanımı, devralma)<br /><br /> IntelliSense<br /><br /> Akıllı etiketler<br /><br /> Kod parçacıkları Yöneticisi<br /><br /> Kod Parçacıkları<br /><br /> Yeniden Düzenle<br /><br /> Asıl listeleme<br /><br /> IntelliSense filtreleme<br /><br /> Kod tanımı penceresi<br /><br /> Uygulama Tasarımcısı<br /><br /> Windows Form Tasarımcısı<br /><br /> Windows Presentation Foundation (WPF) Tasarımcısı|  
|Hata Ayıklama|C# ifade değerlendiricisi<br /><br /> Yerel hata ayıklama<br /><br /> Yönetilen hata ayıklama<br /><br /> Düzenle ve Devam Et<br /><br /> İş parçacıkları arası hata ayıklama<br /><br /> Görselleştirmeleri<br /><br /> DataTips<br /><br /> Yerel hata ayıklama<br /><br /> Komut dosyası hata ayıklaması<br /><br /> Birlikte çalışma hata ayıklama<br /><br /> Tam zamanında (JIT) hata ayıklama<br /><br /> Çok işlemli hata ayıklama<br /><br /> XSLT hata ayıklama<br /><br /> Yerel işlem ekleme<br /><br /> İzleme noktaları<br /><br /> Kesme noktası kısıtlamaları|  
|Veri|Sunucu Gezgini (Basitleştirilmiş - yalnızca verileri)<br /><br /> Verileri için yerel veri bağlama (. MDF veya. MDB)<br /><br /> Nesne veri bağlama<br /><br /> Web hizmetine veri bağlama<br /><br /> Veri denetimleri kümesini<br /><br /> XML Düzenleyicisi<br /><br /> Yerel veritabanı sunucusuna veri bağlama<br /><br /> Veri Kaynakları penceresi|  
|Web|HTML Düzenleyicisi<br /><br /> Web tarayıcısı<br /><br /> Web Forms Tasarımcısı<br /><br /> Web sitesi projesi<br /><br /> Web uygulama projesi|  
|Genişletilebilirlik|VSPackages ve MEF Bileşenleri kullanır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kabuk (Yalıtılmış veya Tümleşik)](shell-isolated-or-integrated.md)
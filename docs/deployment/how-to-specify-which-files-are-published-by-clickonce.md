---
title: 'Nasıl yapılır: ClickOnce tarafından hangi dosyaların yayımlandığını belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.File
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, file exclusion
- files, publishing via ClickOnce
ms.assetid: 579c134a-d50f-4e0c-8e05-2a4ff654896a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c59ffc2324f25c42b505505b0dbea9160ef023a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-which-files-are-published-by-clickonce"></a>Nasıl yapılır: ClickOnce Tarafından Hangi Dosyaların Yayımlandığını Belirtme
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projedeki uygulama, tüm kod olmayan dosyalar uygulama ile birlikte dağıtılır. Bazı durumlarda, değil istediğiniz veya belirli dosyaları yayımlamanız gerekir veya koşullara göre belirli dosyaları yüklemek isteyebilirsiniz. Visual Studio dosyaları dışarıda bırak, dosyaları veri dosyası veya önkoşul işaretlemek ve koşullu yüklemek için dosya grupları oluşturmak için özellikleri sağlar.  
  
 Dosyaları bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama yönetilir **uygulama dosyalarını** iletişim kutusu, erişilebilir **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
 Başlangıçta, adlı tek bir dosya grubu yoktur **(gerekli)**. Ek dosya grupları oluşturun ve bunlara dosyalar atayabilirsiniz. Değiştiremezsiniz **indirme grubu** uygulamayı çalıştırmak için gerekli olan dosyalar için. Örneğin, uygulamanın .exe veya dosyaları veri dosyalarını ait olmalıdır üzere işaretlenmiş **(gerekli)** grubu.  
  
 Varsayılan yayımlama durum ile bir dosya değerini etiketli **(otomatik)**. Örneğin, uygulamanın .exe yayımla durumuna sahip **Ekle (otomatik)** varsayılan olarak.  
  
 İle dosyaları **yapı eylemi** özelliğini **içerik** uygulama dosyaları olarak atanan ve varsayılan olarak dahil olarak işaretlenir. Bunlar eklenebilen, hariç veya veri dosyaları olarak işaretlenmiş. Özel durumlar aşağıdaki gibidir:  
  
-   SQL veritabanı (.mdf ve .mdb) ve XML dosyaları gibi veri dosyalarını varsayılan veri dosyaları olarak işaretlenir.  
  
-   Derlemeler (.dll dosyaları) yönelik başvurular referans eklediğinizde, aşağıdaki gibi atanır: varsa **kopya yerel** olan **False**, varsayılan bir önkoşul derleme olarak işaretlenmiş (**önkoşul ( Otomatik)**), bulunmalıdır GAC'ye uygulama yüklenmeden önce. Varsa **kopya yerel** olan **True**, derleme varsayılan uygulama bütünleştirilmiş olarak işaretlenmiş (**Ekle (otomatik)**) ve yükleme sırasında uygulama klasörüne kopyalanır. Bir COM referansı görünür **uygulama dosyalarını** iletişim kutusu (olarak .ocx dosyası) yalnızca IF kendi **Isolated** özelliği ayarlanmış **doğru**. Varsayılan olarak dahil edilir.  
  
### <a name="to-add-files-to-the-application-files-dialog-box"></a>Uygulama dosyaları iletişim kutusu için dosyaları ekleme  
  
1.  Bir veri dosyası seçin **Çözüm Gezgini**.  
  
2.  Özellikler penceresinde değiştirin **yapı eylemi** özelliğine **içerik** değeri.  
  
### <a name="to-exclude-files-from-clickonce-publishing"></a>ClickOnce yayımlama dosyaları dışlamak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **uygulama dosyalarını** açmak için düğmeye **uygulama dosyalarını** iletişim kutusu.  
  
4.  İçinde **uygulama dosyalarını** iletişim kutusunda, dışlamak istediğiniz dosyayı seçin.  
  
5.  İçinde **yayımlama durumu** alan, select **hariç** aşağı açılan listeden.  
  
### <a name="to-mark-files-as-data-files"></a>Dosyaları veri dosyaları olarak işaretlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **uygulama dosyalarını** açmak için düğmeye **uygulama dosyalarını** iletişim kutusu.  
  
4.  İçinde **uygulama dosyalarını** iletişim kutusunda, dışlamak istediğiniz dosyayı seçin.  
  
5.  İçinde **yayımlama durumu** alan, select **veri dosyası** aşağı açılan listeden.  
  
### <a name="to-mark-files-as-prerequisites"></a>Dosyaları önkoşul olarak işaretlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **uygulama dosyalarını** açmak için düğmeye **uygulama dosyalarını** iletişim kutusu.  
  
4.  İçinde **uygulama dosyalarını** iletişim kutusunda, bir önkoşul işaretlemek istediğiniz uygulama derlemesi (.dll dosyası) seçin. Uygulamanız için bu listesinde görünmesi uygulama derlemesine başvuru olması gerektiğini unutmayın.  
  
5.  İçinde **yayımlama durumu** alan, select **önkoşul** aşağı açılan listeden.  
  
### <a name="to-add-a-new-file-group"></a>Yeni bir dosya grubu eklemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **uygulama dosyalarını** açmak için düğmeye **uygulama dosyalarını** iletişim kutusu.  
  
4.  İçinde **uygulama dosyalarını** iletişim kutusunda **grup** yeni gruba dahil etmek istediğiniz bir dosya için alan.  
  
    > [!NOTE]
    >  Dosyaları olmalıdır **yapı eylemi** özelliğini **içerik** dosya adları görünmesi **uygulama dosyalarını** iletişim kutusu.  
  
5.  İçinde **indirme grubu** alan, select  **\<yeni... >** aşağı açılan listeden.  
  
6.  İçinde **yeni grup** iletişim kutusunda grup için bir ad girin ve ardından **Tamam**.  
  
### <a name="to-add-a-file-to-a-group"></a>Bir gruba bir dosya eklemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **uygulama dosyalarını** açmak için düğmeye **uygulama dosyalarını** iletişim kutusu.  
  
4.  İçinde **uygulama dosyalarını** iletişim kutusunda **grup** yeni gruba dahil etmek istediğiniz bir dosya için alan.  
  
5.  İçinde **indirme grubu** alanında, aşağı açılan listeden bir grup seçin.  
  
    > [!NOTE]
    >  Değiştiremezsiniz **indirme grubu** uygulamayı çalıştırmak için gerekli olan dosyalar için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
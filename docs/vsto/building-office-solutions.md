---
title: "Office çözümleri oluşturma | Microsoft Docs"
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
- debugging [Office development in Visual Studio]
- debugging Office applications in Visual Studio
- solutions [Office development in Visual Studio], debugging
- Office applications [Office development in Visual Studio], debugging
- application development [Office development in Visual Studio], building
- Office applications [Office development in Visual Studio], building
- projects [Office development in Visual Studio], debugging
- Office solutions [Office development in Visual Studio], building
- solutions [Office development in Visual Studio], building
- Office projects [Office development in Visual Studio], debugging
- projects [Office development in Visual Studio], building
- builds [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], building
- application development [Office development in Visual Studio], debugging
- Office solutions [Office development in Visual Studio], debugging
ms.assetid: c4b79ea8-df70-4a72-b76e-26e337d65727
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a3df5fca6d41070b09ceb8b8be9b05212b7caa69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="building-office-solutions"></a>Office Çözümleri Oluşturma
  Genel olarak, derleme ve Office projelerinde hata ayıklama derleme ve diğer türleri Windows Forms gibi Visual Studio projelerinde hata ayıklama aynıdır. Bu bölümdeki konular, mevcut farkları açıklamaktadır. Uygulamaların nasıl yapılandırıldığı hakkında genel bilgi için bkz: [derleme ve Visual Studio'da derleme](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="project-output-for-office-projects"></a>Office projeleri için proje çıktı  
 Office projeleri için çıkış konumu *projectname*\bin\release veya *projectname*\bin\debug'dır. Bir dağıtım dizinine oluşturamaz.  
  
### <a name="document-level-projects"></a>Belge düzeyi projelerine  
 Belge düzeyi projesi derlerken, aşağıdaki öğeler proje çıktısına eklendi:  
  
-   Proje belgenin bir kopyasını.  
  
-   Proje derleme ve sahip tüm başvurulan derlemelerin kendi **kopya yerel** özelliğini **true**.  
  
-   Dosya adı uzantısı .manifest sahip uygulama bildirimi. Daha fazla bilgi için bkz: [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
-   .Application dosya ismi uzantısına sahip olan dağıtım bildirimi. Daha fazla bilgi için bkz: [dağıtım bildirimleri Office çözümleri için](../vsto/deployment-manifests-for-office-solutions.md).  
  
-   Program veritabanı (PDB) dosyası.  
  
> [!NOTE]  
>  Yerel bilgisayar yerine uzak bir konuma bir belge düzeyi çözümü oluşturmak, uygulamanın Güven Merkezi güvenilir konumlar listesinde tam nitelenmiş bir yol ekleyin. Daha fazla bilgi için verme Trust to Documents adlı bölüme bakın [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
### <a name="application-level-projects"></a>Uygulama düzeyi projeleri  
 VSTO eklenti projesindeki oluşturma sırasında aşağıdaki öğeler proje çıktısına eklendi:  
  
-   Proje derleme ve sahip tüm başvurulan derlemelerin kendi **kopya yerel** özelliğini **true**.  
  
-   Dosya adı uzantısı .manifest sahip uygulama bildirimi. Daha fazla bilgi için bkz: [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
-   .Application dosya ismi uzantısına sahip olan dağıtım bildirimi. Daha fazla bilgi için bkz: [dağıtım bildirimleri Office çözümleri için](../vsto/deployment-manifests-for-office-solutions.md).  
  
-   Proje derleme için bir program veritabanı (PDB) dosyası.  
  
 Derleme işlemi için VSTO eklentisi projelerine kayıt defteri girdileri kümesini VSTO eklenti yüklemek için gerekli geliştirme bilgisayarınızda da oluşturur. Daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
 Form bölgeleri içeren Outlook VSTO eklenti projesindeki yapılandırdıysanız, oluşturma işlemi aşağıdaki ek bilgileri kayıt defterine ekler:  
  
-   Bir veya daha fazla form bölgeleri ile ilişkili her ileti sınıfı için bir anahtar.  
  
-   Her form bölgesi ve Outlook VSTO eklenti adını temsil eden ilişkili bir değer için bir giriş.  
  
 Outlook form bölgeleri yüklemek için bu bilgileri gerekir.  
  
## <a name="referenced-assemblies"></a>Başvurulmuş Derlemeler  
 Office çözümleri oluşturma projenizden derlemelere (Sınıf Kitaplığı projelerinde dahil) başvuruda bulunabilir. Her başvurulan derlemeyi adlı bir özelliğe sahiptir **kopya yerel**. **Yerel kopyalama** derleme çıktı dizinine kopyalanıp kopyalanmadığını belirtir. Varsayılan olarak ayarlanır **doğru**. Sahip her başvurulan derlemeyi **kopya yerel** kümesine **true** çıktı dizinine kopyalanır.  
  
## <a name="security-during-the-build-process"></a>Güvenlik Yapılandırma işlemi sırasında  
 Visual Studio çözümü güven oluşturma işlemi sırasında vermek için geliştirme bilgisayarındaki güvenlik ayarlarını otomatik olarak yapılandırır. Bu çözümün, hata ayıklarken çalışmasına olanak sağlar.  
  
 Office projeleri yayımcıyı doğrulamak için sertifikaları kullanır. Visual Studio otomatik olarak Office çözümleri tanımlamak için geçici bir sertifika oluşturur ve geçici bir sertifika güven için geliştirme bilgisayarı yapılandırır.  
  
 Daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
### <a name="network-projects"></a>Ağ projeleri  
 Derleme veya belge konumu bir ağ paylaşımında ise, yerel (kullanıcı düzeyi) güvenlik ilkesini güncelleme çözümün çalışmasına izin vermek için yeterli değil. Bir yönetici, derlemeler ve çözüm çalışmadan önce bir ağ paylaşımında olan belgeler için tam güven makine düzeyinde vermeniz gerekir. Güvenlik ilkesini ayarlama hakkında daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
 Belge düzeyi projelerine belgenin tam konumunu Office güvenilir klasörler listesine eklemelisiniz. Daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
## <a name="changing-the-platform-target"></a>Platform hedefini değiştirme  
 Varsayılan olarak, Office projeleri platform hedefidir **herhangi bir CPU**. Genellikle, bu ayarın değiştirilmemesi. İle oluşturulan office çözümleri **herhangi bir CPU** Microsoft, 32 bit ve 64 bit sürümlerinde çalıştırma ayarı platform hedefi [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] veya [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
 Yalnızca 64 bit sürümlerinde Microsoft çalışacak bir çözüm oluşturuyorsanız x64 için platform hedefi ayarlamalısınız [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] veya [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)], ve çözümünüzü yerel 64 bit API'lerini çağırır. Platform hedefi ayarlarını değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: projeleri hedef platformlar yapılandırma](../ide/how-to-configure-projects-to-target-platforms.md).  
  
 Platform hedefi için x64 ayarlarsanız, 32-bit sürümlerinde Windows veya Office çözümü çalışmaz. Platform hedefi gerektiren bir 64-bit işlemde çalışması için çözüm x64.  
  
## <a name="using-the-clean-command"></a>Temizle komutunu kullanma  
 Oluşturulan proje dosyalarını geliştirme bilgisayardan kaldırmak için kullanabileceğiniz **temiz** komutunu **yapı** menüde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. **Temiz** komut yapı çıktı konumdaki tüm dosyaları siler. Uygulama düzeyi projeleri için **temiz** komutu yapı işlemi tarafından oluşturulan kayıt defteri girdilerini de kaldırır.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Office projelerinde hata ayıklama](../vsto/debugging-office-projects.md)|Office projelerinde hata ayıklama ilgili konuları sunar.|  
|[İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Excel için temel bir belge düzeyi özelleştirme oluşturulacağını gösterir.|  
|[Nasıl yapılır: devre dışı bırakılmış VSTO eklentisinin yeniden etkinleştirin](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)|VSTO yazılım veya devre dışı bırakılmış eklentiyi yeniden etkinleştirmeyi açıklar.|  
|[Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)|Office çözümleri oluşturma ve derlemelerin çözümünüzdeki rolü hakkındaki bilgilere bağlantılar sağlar.|  
  
  
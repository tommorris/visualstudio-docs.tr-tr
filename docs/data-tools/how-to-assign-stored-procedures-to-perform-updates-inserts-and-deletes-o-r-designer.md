---
title: "Güncelleştirme gerçekleştirmek için saklı yordamları Ekle ve LINQ to SQL O/R Tasarımcısı Sil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 20669a4ec19865e99a9498e87e896aa645321257
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>Nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atayın
Saklı yordamlar için O/R Tasarımcısı eklenebilir ve tipik olarak yürütülen <xref:System.Data.Linq.DataContext> yöntemleri. Varsayılan değer geçersiz kılmak için de kullanılabilir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] ekler, güncelleştirmeleri gerçekleştiren ve değişiklikleri veritabanına varlık sınıflardan kaydedildiğinde siler çalışma zamanı davranışı (örneğin, çağrılırken <xref:System.Data.Linq.DataContext.SubmitChanges%2A> yöntemi).  
  
> [!NOTE]
>  Saklı yordam istemciye gönderilmesi gereken değerler döndürürse (örneğin, hesaplanan değerler saklı yordamda), çıktı parametreleri saklı yordamlarda oluşturun. Çıkış parametreleri kullanamıyorsanız, O/R tasarımcısı tarafından oluşturulan yazma güvenmek yerine bir kısmi yöntemi uygulama geçersiz kılar. Veritabanı oluşturulan değerler için eşlenen üyelerinin ekleme veya güncelleştirme işlemleri başarıyla tamamlandıktan sonra uygun değerlere ayarlanmış olması gerekir. Daha fazla bilgi için bkz: [Geliştirici içinde geçersiz kılma varsayılan davranışı sorumluluklarını](/dotnet/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior).  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]veritabanında oluşturulan tanıtıcıları değerleri otomatik olarak kimlik (otomatik artım), rowguıdcol (veritabanında oluşturulan GUID) ve zaman damgası sütunları. Diğer sütun türleri veritabanında oluşturulan değerlerde beklenmedik bir null değer neden olur. Veritabanında oluşturulan değer döndürmek için el ile ayarlamanız gerekir <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> için `true` ve <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> aşağıdakilerden birine: <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync>, veya <xref:System.Data.Linq.Mapping.AutoSync>.  
  
## <a name="configuring-the-update-behavior-of-an-entity-class"></a>Bir varlık sınıfı güncelleştirme davranışını yapılandırma  
 Varsayılan olarak, verilerde yapılan değişikliklerle (ekler, güncelleştirmeleri ve silme) bir veritabanını güncelleştirmek için mantığı [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] sınıflar tarafından sağlanan [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] çalışma zamanı. Çalışma zamanı temel alan INSERT, UPDATE ve DELETE komutları varsayılan oluşturur (sütun ve birincil anahtar bilgilerini) tablonun şeması. Varsayılan davranış değil istendiğinde, gerekli ekler, güncelleştirmeleri ve silme, tablodaki verileri işlemek için gerekli gerçekleştirmek için özel saklı yordamları atayarak güncelleştirme davranışını yapılandırabilirsiniz. Varlık sınıflarınızı görünümlerine eşlediğinizde varsayılan davranışı, örneğin, değil oluşturulduğunda de bunu yapabilirsiniz. Son olarak, veritabanı saklı yordamları aracılığıyla tablo erişim gerektirdiğinde varsayılan güncelleştirme davranışı geçersiz kılabilirsiniz.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>Bir varlık sınıfı varsayılan davranışını geçersiz kılmak için saklı yordamlar atamak için  
  
1.  Açık **LINQ-SQL** Tasarımcısı'nda dosya. (.dbml dosyasına çift tıklayarak **Çözüm Gezgini**.)  
  
2.  İçinde **Sunucu Gezgini**/**Database Explorer**, genişletin **saklı yordamlar** ve INSERT, Update, kullanmak istediğiniz saklı yordamlar bulun ve/veya silme komutlarını varlık sınıfı.  
  
3.  Saklı yordam O/R Tasarımcısı ' sürükleyin.  
  
     Saklı yordam yöntemleri bölmesi olarak eklenen bir <xref:System.Data.Linq.DataContext> yöntemi. Daha fazla bilgi için bkz: [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).  
  
4.  Saklı yordam güncelleştirmeleri gerçekleştirmek için kullanmak istediğiniz varlık sınıfı seçin.  
  
5.  İçinde **özellikleri** penceresinde, geçersiz kılmak için komutu seçin (**Ekle**, **güncelleştirme**, veya **silmek**).  
  
6.  Sözcükleri yanındaki üç nokta işaretine (...) tıklatın **kullanım çalışma zamanı** açmak için **yapılandırma davranışı** iletişim kutusu.  
  
7.  Seçin **özelleştirme**.  
  
8.  İstenen saklı yordamı seçin **Özelleştir** listesi.  
  
9. Listesini inceleyin **yöntem bağımsız değişkenleri** ve **sınıf özelliklerini** doğrulamak için **yöntem bağımsız değişkenleri** uygun harita **sınıf özelliklerini**. Özgün yöntemi bağımsız değişken eşleme (Original_*ArgumentName*) özgün özelliklerine (*PropertyName* (orijinal)) Update ve Delete komutları için.  
  
    > [!NOTE]
    >  Adları eşleştiğinde varsayılan olarak, yöntem bağımsız değişkenleri sınıfın özelliklerine eşlenir. Özellik adlarının artık tablo ve varlık sınıfı arasında eşleştiğini değiştirdiyseniz, Tasarımcı doğru Eşleme belirleyemiyorsa eşlemek için eşdeğer sınıfı özelliği seçin gerekebilir.  
  
10. Tıklatın **Tamam** veya **uygulamak**.  
  
    > [!NOTE]
    >  Tıklattığınız sürece her sınıf/davranışı birleşimi için davranış yapılandırmaya devam edebilirsiniz **Uygula** her değişikliği yaptıktan sonra. Tıklatmadan önce sınıf veya davranışı değiştirirseniz **Uygula**, değişiklikleri uygulamak için bir fırsat görünür sağlayan bir uyarı iletişim kutusu.  
  
Varsayılan çalışma zamanı mantığı güncelleştirmeleri kullanmaya dönmek için INSERT, Update yanındaki üç noktaya tıklayın veya silme komutunu **özellikleri** penceresini açın ve ardından **çalışma zamanı kullanmak** içinde  **Davranışı yapılandırmak** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca bkz.
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[DataContext yöntemleri](../data-tools/datacontext-methods-o-r-designer.md)   
[LINQ-SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)   
[INSERT, Update ve silme işlemleri (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/insert-update-and-delete-operations)
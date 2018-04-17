---
title: 'İzlenecek yol: Tek tablo devralma (O R Tasarımcısı) kullanarak LINQ-SQL sınıfları oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 8a0c6702a965ae2733d2461cf30f5fd91f27dba3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>İzlenecek yol: Tek tablo devralma (O/R Tasarımcısı) kullanarak LINQ-SQL sınıfları oluşturma
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md) ilişkisel sistemlerinde genellikle gerçekleştirilir gibi tek Tablo Devralma destekler. Bu kılavuzda sağlanan genel adımlar üzerine genişletir [nasıl yapılır: devralma O/R Tasarımcısı kullanarak yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) konu ve devralma kullanımını göstermek için gerçek bazı veriler sağlar [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
 Bu gözden geçirme sırasında aşağıdaki görevleri gerçekleştirmeniz gerekecektir:  
  
-   Bir veritabanı tablosu oluşturun ve veri ekleyin.  
  
-   Bir Windows Forms uygulaması oluşturun.  
  
-   Ekleme bir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] bir proje dosyası.  
  
-   Yeni varlık sınıfı oluşturun.  
  
-   Devralma kullanmak için varlık sınıfları yapılandırın.  
  
-   Devralınan sınıfı sorgu.  
  
-   Verileri bir Windows formunda görüntüleyin.  
  
## <a name="create-a-table-to-inherit-from"></a>Devralınacak tablosu oluşturma  
 Devralma nasıl çalıştığını görmek için küçük bir kişinin Tablo oluşturma, temel sınıf olarak kullanın ve devralan çalışan nesne oluşturmak.  
  
#### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>Devralma göstermek için bir temel tablo oluşturmak için  
  
1.  İçinde **Sunucu Gezgini**/**Database Explorer**, sağ **tabloları** düğümü ve tıklatın **Yeni Tablo Ekle**.  
  
    > [!NOTE]
    >  Northwind veritabanı veya bir tabloya ekleyebilirsiniz herhangi bir veritabanını kullanabilirsiniz.  
  
2.  Tablo Tasarımcısı'nda aşağıdaki sütunları tabloya ekleyin:  
  
    |Sütun adı|Veri Türü|Null değerlere izin ver|  
    |-----------------|---------------|-----------------|  
    |**ID**|**int**|**False**|  
    |**Türü**|**int**|**TRUE**|  
    |**FirstName**|**Nvarchar(200)**|**False**|  
    |**Soyadı**|**Nvarchar(200)**|**False**|  
    |**Yöneticisi**|**int**|**TRUE**|  
  
3.  ID sütunu birincil anahtar olarak ayarlayın.  
  
4.  Tabloyu kaydedin ve adlandırın **kişi**.  
  
## <a name="add-data-to-the-table"></a>Tabloya veri ekleme  
 Devralma doğru şekilde yapılandırıldığını doğrulayabilirsiniz böylece tablo bazı veriler tek Tablo Devralma her sınıf için gerekir.  
  
#### <a name="to-add-data-to-the-table"></a>Tabloya veri eklemek için  
  
1.  Tablonun veri görünümünü açın. (Sağ **kişi** tablosundaki **Sunucu Gezgini**/**Database Explorer** tıklatıp **tablo verileri Göster**.)  
  
2.  Aşağıdaki veriler tabloya kopyalayın. (Kopyalayın ve ardından sonuçlar bölmesinde tüm satırı seçerek tablosuna Yapıştır.)  
  
    ||||||  
    |-|-|-|-|-|  
    |**ID**|**Türü**|**FirstName**|**Soyadı**|**Yöneticisi**|  
    |**1**|**1**|**Anne**|**Wallace**|**NULL**|  
    |**2**|**1**|**Carlos**|**Grilo**|**NULL**|  
    |**3**|**1**|**Yael**|**Peled**|**NULL**|  
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|  
    |**5**|**2**|**Andreas**|**Hauser**|**1**|  
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|  
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|  
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|  
    |**9**|**2**|**Tai**|**N**|**2**|  
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|  
    |**11**|**2**|**Kemal**|**Martin**|**3**|  
    |**12**|**2**|**Ken**|**Kwok**|**3**|  
  
## <a name="create-a-new-project"></a>Yeni bir proje oluşturun  
 Tablo oluşturduğunuza göre yapılandırma devralma göstermek için yeni bir proje oluşturun.  
  
#### <a name="to-create-the-new-windows-forms-application"></a>Yeni Windows Forms uygulaması oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **InheritanceWalkthrough**ve ardından **Tamam**. 
  
     **InheritanceWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>Bir LINQ to SQL öğesini ekleme projesine dosyasını sınıfları  
  
#### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>Bir LINQ SQL dosyasına projeye eklemek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  Tıklatın **LINQ'ten SQL'e sınıflarını** şablonu ve ardından **Ekle**.  
  
     .Dbml dosyası projeye eklenir ve [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] açar.  
  
## <a name="create-the-inheritance-by-using-the-or-designer"></a>O/R Tasarımcısı kullanarak devralma oluştur  
 Devralma sürükleyerek yapılandırma bir **devralma** nesnesinin **araç** tasarım yüzeyine.  
  
#### <a name="to-create-the-inheritance"></a>Devralma oluşturmak için  
  
1.  İçinde **Sunucu Gezgini**/**Database Explorer**, gitmek **kişi** daha önce oluşturduğunuz tablo.  
  
2.  Sürükleme **kişi** üzerine tablo [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] tasarım yüzeyi.  
  
3.  İkinci bir sürükleyin **kişi** üzerine tablo [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] adının değiştirip **çalışan**.  
  
4.  Silme **Yöneticisi** özelliğinden **kişi** nesnesi.  
  
5.  Silme **türü**, **kimliği**, **FirstName**, ve **LastName** özelliklerinden **çalışan** nesnesi. (Diğer bir deyişle, dışındaki tüm özellikleri Sil **Yöneticisi**.)  
  
6.  Gelen **Nesne İlişkisel Tasarımcısı** sekmesinde **araç**, oluşturma bir **devralma** arasında **kişi** ve  **Çalışan** nesneleri. Bunu yapmak için tıklatın **devralma** öğesi **araç** ve fare düğmesini bırakın. Bundan sonra öğesini **çalışan** nesnesi ve ardından **kişi** nesnesinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Devralma Satırı Oku işaret edecek **kişi** nesnesi.  
  
7.  Tıklatın **devralma** tasarım yüzeyine satırda.  
  
8.  Ayarlama **Ayrıştırıcıyı özelliği** özelliğine **türü**.  
  
9. Ayarlama **türetilmiş sınıf Ayrıştırıcıyı değeri** özelliğine **2**.  
  
10. Ayarlama **temel sınıf Ayrıştırıcıyı değeri** özelliğine **1**.  
  
11. Ayarlama **devralma varsayılan** özelliğine **kişi**.  
  
12. Projeyi oluşturun.  
  
## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>Devralınan sınıfı sorgulamak ve formdaki verileri görüntüleme  
 Şimdi, belirli bir sınıf nesne modelindeki sorgular form biraz kod ekleyeceksiniz.  
  
#### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>LINQ sorgusu oluşturun ve form üzerinde sonuçları görüntülemek için  
  
1.  Sürükleme bir **ListBox** Form1 üzerine.  
  
2.  Formu oluşturmak için bir `Form1_Load` olay işleyicisi.  
  
3.  Aşağıdaki kodu ekleyin `Form1_Load` olay işleyicisi:  
  
    ```vb  
    Dim dc As New DataClasses1DataContext  
    Dim results = From emp In dc.Persons _  
        Where TypeOf emp Is Employee _  
        Select emp  
  
    For Each Emp As Employee In results  
        ListBox1.Items.Add(Emp.LastName)  
    Next  
    ```  
  
    ```csharp  
    NorthwindDataContext dc = new DataClasses1DataContext();  
    var results = from emp in dc.Persons  
                  where emp is Employee  
                  select emp;  
  
    foreach(Employee Emp in results)  
    {  
        listBox1.Items.Add(Emp.LastName)  
    }  
    ```  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Uygulamayı çalıştırın ve liste kutusunda görüntülenen kayıtları tüm çalışanlar (kendi Türü sütununda 2 değerine sahip kayıtları) olduğundan emin olun.  
  
#### <a name="to-test-the-application"></a>Uygulamayı test etmek için  
  
1.  F5 tuşuna basın.  
  
2.  Yalnızca kendi Türü sütununda 2 değerine sahip kayıtların görüntülendiğini doğrulayın.  
  
3.  Formu kapatın. (Üzerinde **hata ayıklama** menüsünde tıklatın **durdurma hata ayıklama**.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [İzlenecek yol: LINQ-SQL sınıfları (O R Tasarımcısı) oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [Nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atayın](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index)   
 [Nasıl yapılır: Visual Basic veya C# içinde Nesne Modeli Oluşturma](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)
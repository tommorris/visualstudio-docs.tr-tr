---
title: Windows Forms tabanlı bir etki alanına özgü dil oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 23fe0d582f92d5025049974ccd64357203e4845a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Windows Forms Tabanlı Etki Alanına Özgü Dil Oluşturma
Windows Formları DSL diyagramı kullanmak yerine bir etki alanına özgü dil (DSL) modeli durumunu görüntülemek için kullanabilirsiniz. Bu konu size kılavuzluk bir Windows formunda bir DSL bağlama, kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK.  
  
 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2")  
Bir Windows formu kullanıcı Arabirimi ve model Gezgini gösteren bir DSL örneği.  
  
## <a name="creating-a-windows-forms-dsl"></a>Bir Windows Formları DSL oluşturma  
 **En az WinForm Tasarımcısı** DSL şablon kendi gereksinimlerinize uyacak şekilde değiştirebilirsiniz en az bir DSL oluşturur.  
  
#### <a name="to-create-a-minimal-winforms-dsl"></a>En az bir WinForms DSL oluşturmak için  
  
1.  Gelen DSL oluşturma **en az WinForm Tasarımcısı** şablonu.  
  
     Bu kılavuzda, aşağıdaki adları kabul edilir:  
  
    |||  
    |-|-|  
    |Çözüm ve DSL adı|FarmApp|  
    |Ad Alanı|Company.FarmApp|  
  
2.  Şablonu sağlar ilk örneği ile deneyin:  
  
    1.  Tüm Şablonları dönüştürme.  
  
    2.  Derleme ve örnek çalıştırma (**CTRL + F5**).  
  
    3.  Visual Studio deneysel örneği açın `Sample` hata ayıklama proje dosyasında.  
  
         Bir Windows Forms denetiminde görüntülenir dikkat edin.  
  
         Gezgini'nde görüntülenen model öğelerini de görebilirsiniz.  
  
         Bazı öğeler form veya Explorer ekleyin ve diğer görüntüsünü görüntülendiğine dikkat edin.  
  
 Ana örneğindeki [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], aşağıdaki noktaları DSL çözümü hakkında dikkat edin:  
  
-   `DslDefinition.dsl` hiçbir diyagramı öğeleri içerir. Bu DSL örneği modellerinin görüntülemek için DSL diyagramları kullanmayacak olmasıdır. Bunun yerine, bir Windows formunda modele bağlarsınız ve formda öğeleri model görüntüler.  
  
-   Ek olarak `Dsl` ve `DslPackage` projeleri, çözümü içeren adlı üçüncü projesi `UI.` **UI** projesi bir Windows Forms denetimi tanımını içerir. `DslPackage` bağımlı `UI`, ve `UI` bağlıdır `Dsl`.  
  
-   İçinde `DslPackage` projesi `UI\DocView.cs` tanımlanan Windows Forms denetimi görüntüler kodunu içerir `UI` projesi.  
  
-   `UI` Projesi DSL bağlı bir biçim denetimiyle çalışma örneği içerir. Ancak, DSL tanımı değiştiğinde, çalışmaz. `UI` Proje içerir:  
  
    -   Adlı bir Windows Forms sınıf `ModelViewControl`.  
  
    -   Adlı bir dosya `DataBinding.cs` ek bir kısmi tanımını içeren `ModelViewControl`. İçeriği görmek için **Çözüm Gezgini**, dosya için kısayol menüsünü açın ve seçin **görünümü kodu**.  
  
### <a name="about-the-ui-project"></a>UI projesi hakkında  
 Kendi DSL tanımlamak için DSL tanım dosyası güncelleştirdiğinizde denetiminde güncelleştirmeniz gerekir `UI` , DSL görüntülemek için proje. Farklı `Dsl` ve `DslPackage` projeleri, örnek `UI` gelen proje oluşturulmuyor `DslDefinitionl.dsl`. İsterseniz, bu kılavuzda kapsanmayan rağmen kodunu oluşturmak için .tt dosyaları ekleyebilirsiniz.  
  
## <a name="updating-the-dsl-definition"></a>DSL tanım güncelleştirme  
 Aşağıdaki DSL tanımı bu kılavuzda kullanılır.  
  
 ![DSL&#45;Wpf&#45;1](../modeling/media/dsl-wpf-1.png "DSL-Wpf-1")  
  
#### <a name="to-update-the-dsl-definition"></a>DSL tanımı güncelleştirmek için  
  
1.  DslDefinition.dsl DSL Tasarımcısı'nda açın.  
  
2.  Silme **ExampleElement**  
  
3.  Yeniden Adlandır **ExampleModel** etki alanı sınıfına `Farm`.  
  
     Adlı ek bir etki alanı özelliklerini verin `Size` türü **Int32**, ve `IsOrganic` türü **Boolean**.  
  
    > [!NOTE]
    >  Kök etki alanı sınıfını silmek ve ardından yeni bir kökü oluşturursanız, düzenleyici kök sınıf özelliği sıfırlama gerekecektir. İçinde **DSL Explorer**seçin **Düzenleyicisi**. Özellikler penceresini ayarlamak **kök sınıfı** için `Farm`.  
  
4.  Kullanım **adlı etki alanı sınıf** aracı aşağıdaki etki alanı sınıfları oluşturmak için:  
  
    -   `Field` -Bu adlı bir ek etki alanı özellik size `Size`.  
  
    -   `Animal` -Özellikler penceresinde ayarlayın **devralma değiştiricisi** için **soyut**.  
  
5.  Kullanım **etki alanı sınıfı** aracı aşağıdaki sınıflar oluşturmak için:  
  
    -   `Sheep`  
  
    -   `Goat`  
  
6.  Kullanım **devralma** yapmak için aracı `Goat` ve `Sheep` devralınmalıdır `Animal`.  
  
7.  Kullanım **katıştırma** katıştırmak için aracı `Field` ve `Animal` altında `Farm`.  
  
8.  Diyagram tutuyor isteyebilirsiniz. Yinelenen öğe sayısını azaltmak için kullanma **alt ağacı burada Getir** yaprak öğelerinin kısayol menüsünde komutu.  
  
9. **Tüm Şablonları dönüştürme** Çözüm Gezgini araç.  
  
10. Yapı **Dsl** projesi.  
  
    > [!NOTE]
    >  Bu aşamada, diğer projeleri hatasız derleme değil. Ancak, böylece kendi derleme için veri kaynağı Sihirbazı'nı kullanılabilir Dsl Projeyi derlemek istiyoruz.  
  
## <a name="updating-the-ui-project"></a>UI projesini güncelleştirmek  
 Artık DSL modelde depolanan bilgileri görüntüler yeni bir kullanıcı denetimi oluşturabilirsiniz. Veri bağlamaları kullanıcı denetimi modele bağlanmak için en kolay yoludur. Veri bağlama adlı bağdaştırıcı türü **ModelingBindingSource** DSL'ler VMSDK olmayan arabirimlere bağlamak için özel olarak tasarlanmıştır.  
  
#### <a name="to-define-your-dsl-model-as-a-data-source"></a>Bir veri kaynağı olarak DSL modelinizi tanımlamak için  
  
1.  Üzerinde **veri** menüsünde seçin **veri kaynaklarını Göster**.  
  
     **Veri kaynakları** penceresi açılır.  
  
     Seçin **yeni veri kaynağı eklemek**. **Veri kaynağı Yapılandırma Sihirbazı** açar.  
  
2.  Seçin **nesne**, **sonraki**.  
  
     Genişletme **Dsl**, **Company.FarmApp**seçip **grubu**, modelinizi kök sınıfının olduğu. Seçin **son**.  
  
     Çözüm Gezgini'nde, **UI** projesini şimdi içeren **Properties\DataSources\Farm.datasource**  
  
     Özellikler ve ilişkiler modeli sınıfınızın veri kaynakları penceresinde görünür.  
  
     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png "DslWpf-3")  
  
#### <a name="to-connect-your-model-to-a-form"></a>Forma modelinizi bağlanmak için  
  
1.  İçinde **UI** proje, var olan tüm .cs dosyaları silin.  
  
2.  Yeni bir ekleme **kullanıcı denetimi** adlı dosya `FarmControl` için **UI** projesi.  
  
3.  İçinde **veri kaynakları** pencerede açılır menüsünden **grubu**, seçin **ayrıntıları**.  
  
     Diğer özellikler için varsayılan ayarları bırakın.  
  
4.  FarmControl.cs Tasarım görünümünde açın.  
  
     Sürükleme **grubu** FarmControl üzerine veri kaynakları penceresinden.  
  
     Denetimleri kümesini görünür, her bir özellik için bir tane. İlişki özelliklerini denetimleri oluşturmaz.  
  
5.  Silme **farmBindingNavigator**. Bu da otomatik olarak üretildi `FarmControl` Tasarımcısı, ancak bu uygulama için yararlı değildir.  
  
6.  Araç kutusu kullanarak oluşturduğunuz iki örneğini **DataGridView**ve bunları `AnimalGridView` ve `FieldGridView`.  
  
    > [!NOTE]
    >  Bir alternatif hayvanlar ve alanları öğelerini denetimi üzerine veri kaynakları penceresinden sürükleme için adımdır. Bu eylem, veri kılavuzları ve bağlamaları Izgara Görünümü ile veri kaynağı arasında otomatik olarak oluşturur. Ancak, bu bağlama için DSL'ler düzgün çalışmaz. Bu nedenle veri kılavuzları ve bağlamaları oluşturmak daha iyi el ile.  
  
7.  Araç kutusu içermiyorsa **ModelingBindingSource** aracı, ekleyin. Kısayol menüsünden **veri** sekmesinde, seçin **öğeleri Seç**. İçinde **araç kutusu öğelerini Seç** iletişim kutusunda **ModelingBindingSource** gelen **.NET Framework sekmesini**.  
  
8.  Araç kutusu kullanarak oluşturduğunuz iki örneğini **ModelingBindingSource**ve bunları `AnimalBinding` ve `FieldBinding`.  
  
9. Ayarlama **DataSource** her özellik **ModelingBindingSource** için **farmBindingSource**.  
  
     Ayarlama **DataMember** özelliğine **hayvanlar** veya **alanları**.  
  
10. Ayarlama **DataSource** özelliklerini `AnimalGridView` için `AnimalBinding`ve `FieldGridView` için `FieldBinding`.  
  
11. Zevkinize grubu denetimine düzenini ayarlayın.  
  
 **ModelingBindingSource** bir bağdaştırıcı için DSL'ler özgü çeşitli işlevleri gerçekleştirir:  
  
-   Bu güncelleştirmeleri VMSDK deposu işlemde sarmalar.  
  
     Örneğin, kullanıcı bir satır veri görünümü kılavuzundan sildiğinde, normal bir bağlama bir işlem özel neden olur.  
  
-   Kullanıcı bir satır seçtiğinde Özellikler penceresini veri kılavuz satırı yerine karşılık gelen model öğesi özelliklerini görüntüler, sağlar.  
  
 ![DslWpf4](../modeling/media/dslwpf4.png "DslWpf4")  
Veri kaynakları ve görünümler arasında bağlantılar şema.  
  
#### <a name="to-complete-the-bindings-to-the-dsl"></a>DSL bağlamalar tamamlamak için  
  
1.  Ayrı kod dosyasında aşağıdaki kodu ekleyin **UI** proje:  
  
    ```csharp  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Modeling;  
    using Microsoft.VisualStudio.Modeling.Design;  
  
    namespace Company.FarmApp  
    {  
      partial class FarmControl  
      {  
        public IContainer Components { get { return components; } }  
  
        /// <summary>Binds the WinForms data source to the DSL model.  
        /// </summary>  
        /// <param name="nodelRoot">The root element of the model.</param>  
        public void DataBind(ModelElement modelRoot)  
        {  
          WinFormsDataBindingHelper.PreInitializeDataSources(this);  
          this.farmBindingSource.DataSource = modelRoot;  
          WinFormsDataBindingHelper.InitializeDataSources(this);  
        }  
      }  
    }  
    ```  
  
2.  İçinde **DslPackage** proje, düzenleme **DslPackage\DocView.tt** aşağıdaki değişken tanımını güncelleştirmek için:  
  
    ```csharp  
    string viewControlTypeName = "FarmControl";  
    ```  
  
## <a name="testing-the-dsl"></a>DSL test etme  
 DSL çözüm şimdi oluşturun ve daha fazla geliştirmeleri daha sonra eklemek isteyebilirsiniz ancak çalıştırın.  
  
#### <a name="to-test-the-dsl"></a>DSL sınamak için  
  
1.  Derleme ve çözümü çalıştırın.  
  
2.  Visual Studio deneysel örneği açın **örnek** dosya.  
  
3.  İçinde **FarmApp Explorer**, kısayol menüsünü açmak **grubu** kök düğümü ve seçin **ekleme yeni Goat**.  
  
     `Goat1` görünür **hayvanlar** görünümü.  
  
    > [!WARNING]
    >  Kısayol menüsünün kullanmanız gerekir **grubu** düğümü değil **hayvanlar** düğümü.  
  
4.  Seçin **grubu** kök düğümü ve özelliklerini görüntüleyin.  
  
     Form görünümünde değiştirme **adı** veya **boyutu** grubunun.  
  
     Ne zaman her bir alan formunda, karşılık gelen özellik değişikliklerini Özellikleri penceresinde başka bir sayfaya geçemezsiniz.  
  
## <a name="enhancing-the-dsl"></a>DSL geliştirme  
  
#### <a name="to-make-the-properties-update-immediately"></a>Hemen güncelleştirme özellikleri yapma  
  
1.  FarmControl.cs Tasarım görünümünde adı, boyut veya IsOrganic gibi basit bir alan seçin.  
  
2.  Özellikler penceresinde **veri bağlamaları** açarak **(Gelişmiş)**.  
  
     İçinde **biçimlendirme ve Gelişmiş bağlama** iletişim altında **veri kaynağı güncelleme modu**, seçin **OnPropertyChanged**.  
  
3.  Derleme ve çözümü çalıştırın.  
  
     Karşılık gelen özelliği grubu model değişiklikleri hemen alanın içeriği değiştirdiğinizde doğrulayın.  
  
#### <a name="to-provide-add-buttons"></a>Ekle sağlamak için düğmeler  
  
1.  FarmControl.cs Tasarım görünümünde, araç formda bir düğme oluşturmak için kullanın.  
  
     Düğmenin metni ve adını örneğin için Düzenle `New Sheep`.  
  
2.  (Düğme arka plan kod örneğin çift tıklatarak) açın.  
  
     Şu şekilde düzenleyin:  
  
    ```csharp  
    private void NewSheepButton_Click(object sender, EventArgs e)  
    {  
      using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))  
      {  
        elementOperations.MergeElementGroup(farm,  
          new ElementGroup(new Sheep(farm.Partition)));  
        t.Commit();  
      }  
    }  
  
    // The following code is shared with other add buttons:  
    private ElementOperations operationsCache = null;  
    private ElementOperations elementOperations  
    {  
      get  
      {  
        if (operationsCache == null)  
        {  
          operationsCache = new ElementOperations(farm.Store, farm.Partition);  
        }  
        return operationsCache;  
      }  
    }  
    private Farm farm  
    {  
      get { return this.farmBindingSource.DataSource as Farm; }  
    }  
  
    ```  
  
     Aşağıdaki yönergesi eklemek gerekir:  
  
    ```csharp  
  
    using Microsoft.VisualStudio.Modeling;  
  
    ```  
  
3.  Benzer düğmeleri Goats ve alanları ekleyin.  
  
4.  Derleme ve çözümü çalıştırın.  
  
5.  Yeni düğmesini bir öğe ekler doğrulayın. Yeni öğe FarmApp Explorer'da ve uygun veri ızgara görünümünde görüntülenmesi gerekir.  
  
     Veri ızgara görünümünde öğesinin adını düzenlemeniz mümkün olması gerekir. Ayrıca, buradan silebilirsiniz.  
  
 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2")  
  
### <a name="about-the-code-to-add-an-element"></a>Bir öğe eklemek için kod hakkında  
 Yeni öğe düğmeler için aşağıdaki diğer kod biraz daha basittir.  
  
```csharp  
private void NewSheepButton_Click(object sender, EventArgs e)  
{  
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))  
  {  
    farm.Animals.Add(new Sheep(farm.Partition)); ;  
    t.Commit();  
  }  
}  
  
```  
  
 Ancak, bu kod yeni öğe için bir varsayılan ad ayarlı değil. İçinde tanımlanan tüm özelleştirilmiş birleştirme çalışmaz **öğesi birleştirme yönergeleri** DSL, ve tanımlanmış herhangi bir özel birleştirme kod çalıştırmaz.  
  
 Bu nedenle, kullanmanızı öneririz <xref:Microsoft.VisualStudio.Modeling.ElementOperations> yeni öğeleri oluşturmak için. Daha fazla bilgi için bkz: [özelleştirme öğesi oluşturma ve taşıma](../modeling/customizing-element-creation-and-movement.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)   
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Visual Studio için Modelleme SDK'sı - Etki Alanına Özgü Diller](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)
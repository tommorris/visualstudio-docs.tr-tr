---
title: "Bir Windows formunda bir diyagram katıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c5f77fe45fd4289a442f151ff8d1174e68b353bc
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="embedding-a-diagram-in-a-windows-form"></a>Windows Forms'a Diyagram Ekleme
Windows denetiminde hangi görünür, DSL diyagramı katıştırmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] penceresi.  
  
## <a name="embedding-a-diagram"></a>Bir diyagram katıştırma  
  
#### <a name="to-embed-a-dsl-diagram-in-a-windows-control"></a>Bir Windows denetiminde DSL diyagramı eklemek için  
  
1.  Yeni bir ekleme **kullanıcı denetimi** DslPackage projesine dosyasını.  
  
2.  Panel denetimi kullanıcı denetimine ekleyin. Bu panoyu DSL diyagramı içerir.  
  
     İhtiyaç duyduğunuz diğer denetimleri ekleyin.  
  
     Denetimlerin bağlantı özelliklerini ayarlayın.  
  
3.  Çözüm Gezgini'nde, kullanıcı denetimi dosyasını sağ tıklatıp **görünümü kodu**. Bu oluşturucu ve değişken kodu ekleyin:  
  
    ```csharp  
  
    internal UserControl1(MyDSLDocView docView, Control content)  
      : this()  
    {  
      panel1.Controls.Add(content);  
      this.docView = docView;  
    }  
    private MyDSLDSLDocView docView;  
  
    ```  
  
4.  Aşağıdaki içeriğe sahip DslPackage proje için yeni bir dosya ekleyin:  
  
    ```  
    using System.Windows.Forms;  
    namespace Company.MyDSL  
    {  
      partial class MyDSLDocView  
      {  
        private UserControl1 container;  
        public override IWin32Window Window  
        {  
          get  
          {  
            if (container == null)  
            {  
              // Put our own form inside the DSL window:  
              container = new UserControl1(this,  
                (Control)base.Window);  
            }  
            return container;  
    } } } }  
  
    ```  
  
5.  DSL sınamak için F5 tuşuna basın ve bir örnek model dosyasını açın. Diyagram içindeki denetim görünür. Araç kutusu ve diğer özellikleri normal şekilde çalışır.  
  
#### <a name="updating-the-form-using-store-events"></a>Formu deposu olayları kullanarak güncelleştirme  
  
1.  Form Tasarımcısı'nda eklemek bir **ListBox** adlı `listBox1`. Bu öğeleri listesini modelde görüntüler. Kullanarak modeli ile synchronism içinde tutulacak *olayları depolamak*. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
2.  Özel kod dosyasında daha fazla ile DocView sınıfı yöntemleri geçersiz kılın:  
  
    ```  
  
    partial class MyDSLDocView  
    {  
     /// <summary>  
     /// Register store event listeners.  
     /// This method is called when the model and diagram    
     /// have completed loading.   
     /// </summary>  
     protected override bool LoadView()  
      {  
        bool result = base.LoadView();  
        Store store = this.DocData.Store;  
        EventManagerDirectory emd = store.EventManagerDirectory;  
        DomainClassInfo componentClass = store.DomainDataDirectory.FindDomainClass(typeof(ExampleElement));  
        emd.ElementAdded.Add(componentClass, new EventHandler<ElementAddedEventArgs>(AddElement));  
        emd.ElementDeleted.Add(componentClass, new EventHandler<ElementDeletedEventArgs>(RemoveElement));  
  
        // Do the initial parts list:  
        container.SetUpFormFromModel();  
        return result;  
      }  
     /// <summary>  
     /// Listener method called on creation of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void AddElement(object sender, ElementAddedEventArgs e)  
     {  
       container.Add(e.ModelElement as ExampleElement);  
     }  
     /// <summary>  
     /// Listener method called after deletion of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void RemoveElement(object sender, ElementDeletedEventArgs e)  
     {  
       container.Remove(e.ModelElement as ExampleElement);  
     }  
  
    ```  
  
3.  Kullanıcı denetiminin arkasındaki kodda için eklenebilir ve Kaldırılabilir öğeleri dinlemek için yöntemleri ekleyin:  
  
    ```  
  
          public partial class UserControl1 : UserControl { ...  
  
    private ExampleModel modelRoot;  
  
    internal void Add(ExampleElement e) { UpdatePartsList(); }  
    internal void Remove(ExampleElement e) { UpdatePartsList(); }  
  
    internal void SetUpFormFromModel()  
    {  
      modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;  
      UpdatePartsList();  
    }  
  
    private void UpdatePartsList()  
    {  
      StringBuilder builder = new StringBuilder();  
      listBox1.Items.Clear();  
      foreach (ExampleElement c in modelRoot.Elements)  
      {  
        listBox1.Items.Add(c.Name);  
      }  
    }  
  
    ```  
  
4.  DSL test etmek için F5 tuşuna basın ve deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], örnek model dosyasını açın.  
  
     Liste kutusu modeldeki öğelerin bir listesini gösterir ve herhangi bir ekleme veya silme işlemi ve geri alma ve yineleme sonrasında doğru olduğundan emin dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)
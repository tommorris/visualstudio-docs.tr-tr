---
title: "Bir etki alanına özgü dil tanımına izleme özellik ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking properties [Domain-Specific Language Tools], walkthrough
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 21e31bd582fda7884f0f246bd6eda39e5e89a375
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="adding-a-tracking-property-to-a-domain-specific-language-definition"></a>Etki Alanına Özgü Dil Tanımıma İzleme Özelliği Ekleme
Bu kılavuz, bir etki alanı modeline izleme özelliği eklemek gösterilmiştir.  
  
 A *etki alanı izleme* özelliği kullanıcı tarafından güncelleştirilebilir ancak diğer etki alanı özellikleri veya öğelerin değerleri kullanılarak hesaplanan bir varsayılan değere sahip bir özelliğidir.  
  
 Örneğin, etki alanına özgü dil Araçları (DSL araçları), bir etki alanı sınıfının özelliği etki alanı sınıfı, ancak bir kullanıcı adı kullanılarak hesaplanan bir varsayılan değere sahip görünen ad değeri tasarım zamanında değiştirebilir veya hesaplanan değerin sıfırlayın.  
  
 Bu kılavuzda, model varsayılan Namespace özelliğine dayalı bir varsayılan değere sahip özelliği izleme Namespace sahip bir etki alanına özgü dil (DSL) oluşturun. Özellikler izleme hakkında daha fazla bilgi için bkz: [izleme özellikleri tanımlama](http://msdn.microsoft.com/0538b0e4-6221-4e7d-911a-b92cd622f0be).  
  
-   Özellik tanımlayıcılarının izleme DSL Araçlar desteği. Ancak, DSL Tasarımcısı izleme özelliği için bir dil eklemek için kullanılamaz. Bu nedenle, tanımlama ve izleme özelliği uygulamak için özel kod eklemeniz gerekir.  
  
 İki durumlu bir izleme özelliği vardır: izleme ve kullanıcı tarafından güncelleştirildi. İzleme özellikleri aşağıdaki özelliklere sahiptir:  
  
-   Durumundayken izleme, izleme özelliğinin değeri hesaplanır ve değer model değişikliği diğer özellikleri olarak güncelleştirilir.  
  
-   Güncelleştirilmiş durumlarda kullanıcı durumu, izleme özelliğinin değeri, kullanıcı son özellik değeri ayarlanmış korur.  
  
-   İçinde **özellikleri** penceresinde **sıfırlama** özelliği güncelleştirilmiş içinde olduğunda yalnızca izleme özelliği etkinleştirilmişse komutu kullanıcı durumuna göre. **Sıfırlama** komut izleme özelliği ayarlar izleme durumu.  
  
-   İçinde **özellikleri** izleme özelliği değeri izleme durumunda olduğunda penceresinde, normal bir yazı tipiyle görüntülenir.  
  
-   İçinde **özellikleri** izleme özelliği güncelleştirilmiş olduğunda penceresinde, kullanıcı durumu, kalın yazı tipiyle değeri görüntülenir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda başlamadan önce bu bileşenleri yüklemeniz gerekir:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkID=185579](http://go.microsoft.com/fwlink/?LinkID=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkID=185580](http://go.microsoft.com/fwlink/?LinkID=185580)|  
|[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]|[http://go.microsoft.com/fwlink/?LinkID=185581](http://go.microsoft.com/fwlink/?LinkID=185581)|  
  
## <a name="creating-the-dsl-project"></a>DSL projesi oluşturma  
 Etki alanına özgü dil projesi oluşturun.  
  
#### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
1.  Bir etki alanına özgü dil Tasarımcısı projesi oluşturun. Bu ad `TrackingPropertyDSL`.  
  
2.  İçinde **etki alanına özgü dil Tasarımcısı Sihirbazı**, aşağıdaki seçenekleri belirleyin:  
  
    1.  Seçin **MinimalLanguage** şablonu.  
  
    2.  Etki alanına özgü dil için varsayılan adı kullanacak `TrackingPropertyDSL`.  
  
    3.  Model dosyalarının uzantısı `trackingPropertyDsl`.  
  
    4.  Varsayılan şablon simgesi için model dosyaları kullanın.  
  
    5.  Ürün adını ayarlamak `Product Name`.  
  
    6.  Şirket adını ayarlamak `Company Name`.  
  
    7.  Çözümdeki projeler için kök ad alanı için varsayılan değeri kullanın `CompanyName.ProductName.TrackingPropertyDSL`.  
  
    8.  Derlemeleriniz için güçlü ad anahtar dosyası oluşturmak için Sihirbazı izin verin.  
  
    9. Çözüm ayrıntılarını gözden geçirin ve ardından **son** DSL tanımı projesi oluşturmak için.  
  
## <a name="customizing-the-default-dsl-definition"></a>Varsayılan DSL tanımını özelleştirme  
 Bu bölümde, aşağıdaki öğeleri içeren DSL tanımı Özelleştir:  
  
-   Modelin her öğe için özellik izleme Namespace.  
  
-   Modelin her öğe için bir Boolean IsNamespaceTracking özellik. Bu özelliği izleme özelliği durumunu izlemek veya güncelleştirilmiş olup olmadığını gösteren kullanıcı durumuna göre.  
  
-   Model için varsayılan Namespace özelliği. Bu özellik, özellik izleme Namespace varsayılan değerini hesaplamak için kullanılır.  
  
-   Model için hesaplanan CustomElements özelliği. Bu özellik, özel bir ad alanına sahip öğeleri oranını gösterir.  
  
#### <a name="to-add-the-domain-properties"></a>Etki alanı özellikleri eklemek için  
  
1.  DSL Tasarımcısı'nda sağ **ExampleModel** etki alanı sınıfı, noktasına **Ekle**ve ardından **Domainproperty'si**.  
  
    1.  Yeni özellik adı `DefaultNamespace`.  
  
    2.  İçinde **özellikleri** penceresi yeni bir özellik için ayarlanmış **varsayılan değer** için `DefaultNamespace`ve **türü** için **dize**.  
  
2.  İçin **ExampleModel** etki alanı sınıfı, adlı etki alanı özellik ekleme `CustomElements`.  
  
     İçinde **özellikleri** penceresi yeni bir özellik için ayarlanmış **türü** için **hesaplanan**.  
  
3.  İçin **ExampleElement** etki alanı sınıfı, adlı etki alanı özellik ekleme `Namespace`.  
  
     İçinde **özellikleri** penceresi yeni bir özellik için ayarlanmış **olan gözatılamaz** için **False**ve **türü** için **CustomStorage** .  
  
4.  İçin **ExampleElement** etki alanı sınıfı, adlı etki alanı özellik ekleme `IsNamespaceTracking`.  
  
     İçinde **özellikleri** penceresi yeni bir özellik için ayarlanmış **olan gözatılamaz** için **False**ayarlayın **varsayılan değer** için `true`ve ayarlayın **Türü** için **Boolean**.  
  
#### <a name="to-update-the-diagram-elements-and-dsl-details"></a>Diyagram öğeleri ve DSL ayrıntıları güncelleştirmek için  
  
1.  DSL Tasarımcısı'nda sağ **ExampleShape** geometri şekli, noktasına **Ekle**ve ardından **metin oluşturma öğesi**.  
  
    1.  Yeni metin oluşturma öğesi adı `NamespaceDecorator`.  
  
    2.  İçinde **özellikleri** penceresi metin oluşturma öğesi için ayarlanmış **konumu** için **InnerBottomLeft**.  
  
2.  DSL Tasarımcısı'nda bağlayan çizgiyi seçin **ExampleElement** sınıfının **ExampleShape** şekli.  
  
    1.  İçinde **DSL ayrıntıları** penceresinde, seçin **oluşturma öğesi eşlemeleri** sekmesi.  
  
    2.  İçinde **dekoratörler** listesinden **NamespaceDecorator**, onay kutusunu seçin ve ardından **görüntüleme özelliği** listesinden **Namespace**.  
  
3.  İçinde **DSL Explorer**, genişletin **etki alanı sınıflarını** klasörünü sağ tıklatın **ExampleElement** düğümünü ve ardından **ekleme yeni etki alanı tür tanımlayıcı**.  
  
    1.  Genişletme **ExampleElement** düğümü ve select **özel tür tanımlayıcı (etki alanı türü tanımlayıcısı)** düğümü.  
  
    2.  İçinde **özellikleri** penceresi etki alanı tür tanımlayıcısı için ayarlanmış **özel kodlanmış** için **doğru**.  
  
4.  İçinde **DSL Explorer**seçin **Xml serileştirme davranışı** düğümü.  
  
    1.  İçinde **özellikleri** penceresindeki ayarlayın **özel Post yük** için **doğru**.  
  
## <a name="transforming-templates"></a>Şablonları dönüştürme  
 Etki alanı sınıfları ve özellikleri, DSL için tanımladığınız, DSL tanımı projeniz için kodunu yeniden üretmek için doğru dönüştürülebilir doğrulayabilirsiniz.  
  
#### <a name="to-transform-the-text-templates"></a>Metin şablonları dönüştürmek için  
  
1.  Üzerinde **Çözüm Gezgini** araç tıklatın **tüm şablonları dönüştürme**.  
  
2.  Sistem, çözüm için kod oluşturur ve DslDefinition.dsl kaydeder. Tanım dosyalarını XML biçimi hakkında daha fazla bilgi için bkz: [DslDefinition.dsl dosyası](../modeling/the-dsldefinition-dsl-file.md).  
  
## <a name="creating-files-for-custom-code"></a>Dosyalar için özel kod oluşturma  
 Tüm Şablonları dönüştürme, sistem, etki alanına özgü dil Dsl ve DslPackage projelerinde tanımlayan kaynak kodunu oluşturur. Oluşturulan metinle engellemesini önleyebilirsiniz böylece oluşturulan kod dosyalarından ayrı dosyalarında özel kodunuzu yazın.  
  
 Değer ve izleme özelliği durumunu sürdürmek için kod sağlamanız gerekir. Özel kod oluşturulan koddan ayırt yardımcı olması ve dosya adlandırma çakışmaları önlemek için özel kod dosyalarınızın ayrı bir alt klasöre yerleştirin.  
  
#### <a name="to-create-the-code-files"></a>Kod dosyaları oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **DSL** proje, fareyle **Ekle**ve ardından **yeni klasör**. Yeni bir klasör adı `CustomCode`.  
  
2.  Yeni sağ **da** klasörünü **Ekle**ve ardından **yeni öğe**.  
  
3.  Seçin **kod dosyası** şablonu, **adı** için `NamespaceTrackingProperty.cs`ve ardından **Tamam**.  
  
     NamespaceTrackingProperty.cs dosya oluşturulur ve düzenleme için açıldı.  
  
4.  Aşağıdaki kod dosyaları klasöründe oluşturun: `ExampleModel.cs,``HelperClasses.cs`, `Serialization.cs`, ve `TypeDescriptor.cs`.  
  
5.  İçinde **DslPackage** proje, ayrıca Oluştur bir `CustomCode` klasörünü ve ekleyin bir `Package.cs` kod dosyası.  
  
## <a name="adding-helper-classes-to-support-tracking-properties"></a>Özellikler izleme desteklemeye yardımcı sınıfları ekleme  
 HelperClasses.cs dosyasına ekleyin `TrackingHelper` ve `CriticalException` gibi sınıfları. Bu kılavuzda daha sonra bu sınıfların başvurur.  
  
#### <a name="to-add-the-helper-classes"></a>Yardımcı sınıfları eklemek için  
  
1.  HelperClasses.cs dosyasına aşağıdaki kodu ekleyin.  
  
    ```csharp  
    using System;  
    using System.Collections;  
    using System.Diagnostics;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        internal static class TrackingHelper  
        {  
            /// <summary>Notify each model element in a collection that a tracked  
            /// property has changed.</summary>  
            /// <param name="store">The store for the model.</param>  
            /// <param name="collection">The collection of model elements that  
            /// contain the tracking property.</param>  
            /// <param name="propertyId">The ID of the tracking property.</param>  
            /// <param name="trackingPropertyId">The ID of the property that  
            /// indicates whether the tracking property is tracking.</param>  
            internal static void UpdateTrackingCollectionProperty(  
                Store store,  
                IEnumerable collection,  
                Guid propertyId,  
                Guid trackingPropertyId)  
            {  
                DomainPropertyInfo propInfo =  
                    store.DomainDataDirectory.GetDomainProperty(propertyId);  
  
                DomainPropertyInfo trackingPropInfo =  
                    store.DomainDataDirectory.GetDomainProperty(trackingPropertyId);  
  
                Debug.Assert(propInfo != null);  
                Debug.Assert(trackingPropInfo != null);  
                Debug.Assert(trackingPropInfo.PropertyType.Equals(typeof(bool)),  
                    "Tracking property not specified as a boolean");  
  
                foreach (ModelElement element in collection)  
                {  
                    // If the tracking property is currently tracking, then notify  
                    // it that the tracked property has changed.  
                    bool isTracking = (bool)trackingPropInfo.GetValue(element);  
                    if (isTracking)  
                    {  
                        propInfo.NotifyValueChange(element);  
                    }  
                }  
            }  
        }  
  
        /// <summary>Helper class to flag critical exceptions from ones that are  
        /// safe to ignore.</summary>  
        internal static class CriticalException  
        {  
            /// <summary>Gets whether an exception is critical and can not be  
            /// ignored.</summary>  
            /// <param name="ex">The exception to check.</param>  
            /// <returns>True if the exception is critical.</returns>  
            internal static bool IsCriticalException(Exception ex)  
            {  
                if (ex is NullReferenceException  
                    || ex is StackOverflowException  
                    || ex is OutOfMemoryException  
                    || ex is System.Threading.ThreadAbortException)  
                    return true;  
  
                if (ex.InnerException != null)  
                    return IsCriticalException(ex.InnerException);  
  
                return false;  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-custom-type-descriptor"></a>Özel tür tanımlayıcı için özel kod ekleme  
 Uygulama `GetCustomProperties` yöntemi türü tanımlayıcısı için `ExampleModel` etki alanı sınıfı.  
  
> [!NOTE]
>  Özel tür tanımlayıcı için DSL araçları üret kod `ExampleModel` çağrıları `GetCustomProperties`; ancak, DSL araçları yöntemi uygulayan kod oluşturmaz.  
  
 Bu yöntem tanımlama oluşturur izleme özelliği izleme Namespace özellik tanımlayıcısı. Ayrıca, izleme özelliği için öznitelikler sağlama sağlar **özellikleri** özelliği doğru bir şekilde görüntülemek için penceresi.  
  
#### <a name="to-modify-the-type-descriptor-for-the-examplemodel-domain-class"></a>Tür tanımlayıcısı ExampleModel etki alanı sınıfının değiştirmek için  
  
1.  TypeDescriptor.cs dosyasına aşağıdaki kodu ekleyin.  

    ```csharp  
    using System;  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Modeling;  
    using Microsoft.VisualStudio.Modeling.Design;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // To the custom type descriptor for the ExampleElement domain class, add  
        // the GetCustomProperties method.  
        public partial class ExampleElementTypeDescriptor  
        {  
            /// <summary>Returns the property descriptors for the described  
            /// ExampleElement domain class.</summary>  
            /// <remarks>This method adds the tracking property descriptor.  
            /// </remarks>  
            private PropertyDescriptorCollection GetCustomProperties(  
                Attribute[] attributes)  
            {  
                // Get the default property descriptors from the base class  
                PropertyDescriptorCollection propertyDescriptors =  
                    base.GetProperties(attributes);  
  
                // Get a reference to the model element that is being described.  
                ExampleElement source = this.ModelElement as ExampleElement;  
  
                //Add the descriptor for the tracking property.  
                if (source != null)  
                {  
                    DomainPropertyInfo domainProperty =  
                        source.Store.DomainDataDirectory.GetDomainProperty(  
                            ExampleElement.NamespaceDomainPropertyId);  
  
                    DomainPropertyInfo trackingProperty =  
                        source.Store.DomainDataDirectory.GetDomainProperty(  
                            ExampleElement.IsNamespaceTrackingDomainPropertyId);  
  
                    // Define attributes for the tracking property so that the  
                    // Properties window displays the property correctly.  
                    Attribute[] attr = new Attribute[] {  
                        new DisplayNameAttribute("Element Namespace"),  
                        new DescriptionAttribute("The namespace of the element."),  
                        new CategoryAttribute("Tracking Properties"),  
                    };  
  
                    propertyDescriptors.Add(new TrackingPropertyDescriptor(  
                        source, domainProperty, trackingProperty, attr));  
                }  
  
                // Return the property descriptors for this element  
                return propertyDescriptors;  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-package"></a>Paket için özel kod ekleme  
 Oluşturulan kod ExampleElement etki alanı sınıfının bir türü açıklaması sağlayıcı tanımlar; Ancak, bu tür açıklaması sağlayıcısı kullanmak için DSL istemek üzere kod eklemeniz gerekir.  
  
#### <a name="to-update-the-dsl-package-to-use-your-custom-type-descriptor"></a>Özel tür açıklayıcı kullanılacak DSL paketi güncelleştirmek için  
  
1.  Package.cs dosyasına aşağıdaki kodu ekleyin.  
  
    ```csharp  
    using System.ComponentModel;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // Override the default Initialize method.  
        internal sealed partial class TrackingPropertyDSLPackage  
        {  
            protected override void Initialize()  
            {  
                // Add the custom type descriptor for the ExampleElement type.  
                TypeDescriptor.AddProvider(  
                    new ExampleElementTypeDescriptionProvider(),  
                    typeof(ExampleElement));  
  
                base.Initialize();  
            }  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-model"></a>Model için özel kod ekleme  
 Uygulama `GetCustomElementsValue` yöntemi `ExampleModel` etki alanı sınıfı.  
  
> [!NOTE]
>  İçin DSL araçları üret kod `ExampleModel` çağrıları `GetCustomElementsValue`; ancak, DSL araçları yöntemi uygulayan kod oluşturmaz.  
  
 Tanımlama `GetCustomElementsValue` yöntemi hesaplanan CustomElements özelliği için mantığı sağlar `ExampleModel`. Bu yöntem sayar `ExampleElement` , kullanıcı güncelleştirilmiş bir değeri yok ve bu sayı bir kısmının modeldeki toplam öğeleri olarak temsil eden bir dize döndürür özelliği izleme Namespace olan etki alanı sınıf.  
  
 Ayrıca, ekleme bir `OnDefaultNamespaceChanged` yönteme `ExampleModel`ve geçersiz kılma `OnValueChanged` yöntemi `DefaultNamespacePropertyHandler` sınıfının iç içe geçmiş `ExampleModel` çağırmak için `OnDefaultNamespaceChanged`.  
  
 DefaultNamespace özelliği özelliği, izleme Namespace hesaplamak için kullanılır çünkü `ExampleModel` tüm üzerindedir `ExampleElement` DefaultNamespace değeri değiştirildi etki alanı sınıfları.  
  
#### <a name="to-modify-the-property-handler-for-the-tracked-property"></a>İzlenen bir özellik için özellik işleyicisi değiştirmek için  
  
1.  ExampleModel.cs dosyasına aşağıdaki kodu ekleyin.  
  
    ```csharp  
    using System.Linq;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        public partial class ExampleModel  
        {  
            public string GetCustomElementsValue()  
            {  
                if (this.Elements.Count == 0) return "0/0";  
  
                int number = this.Elements.Count(e => !e.IsNamespaceTracking);  
                return string.Format("{0}/{1}", number, this.Elements.Count);  
            }  
  
            #region Value changed handler for the tracked property  
  
            // When a tracked property changes, it needs to notify all of the properties  
            // that track it.  
  
            /// <summary>Called by the DefaultNamespace property value handler when the  
            /// DefaultNamespace property changes.</summary>  
            /// <param name="oldValue">The previous value of the property.</param>  
            /// <param name="newValue">The new value of the property.</param>  
            protected virtual void OnDefaultNamespaceChanged(  
                string oldValue, string newValue)  
            {  
                // Use the helper class to notify all of the elements in the model  
                // that the default namespace has changed.  
                TrackingHelper.UpdateTrackingCollectionProperty(  
                    this.Store,  
                    this.Elements,  
                    ExampleElement.NamespaceDomainPropertyId,  
                    ExampleElement.IsNamespaceTrackingDomainPropertyId);  
            }  
  
            // Update the change handler for the DefaultNamespace property.  
            internal sealed partial class DefaultNamespacePropertyHandler  
            {  
                /// <summary>Called when the DefaultNamespace property changes.</summary>  
                /// <param name="element">The model element that has the property that  
                /// changed.</param>  
                /// <param name="oldValue">The previous value of the property.</param>  
                /// <param name="newValue">The new value of the property.</param>  
                protected override void OnValueChanged(  
                    ExampleModel element, string oldValue, string newValue)  
                {  
                    base.OnValueChanged(element, oldValue, newValue);  
  
                    if (!element.Store.InUndoRedoOrRollback)  
                    {  
                        element.OnDefaultNamespaceChanged(oldValue, newValue);  
                    }  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-for-the-tracking-property"></a>İzleme özelliği için özel kod ekleme  
 Ekleme bir `CalculateNamespace` yönteme `ExampleElement` etki alanı sınıfı.  
  
 Bu yöntem tanımlamak, hesaplanan CustomElements özelliği için mantığı sağlar `ExampleModel`. Bu yöntem sayar `ExampleElement` güncelleştirilmiş olan özellik izleme Namespace sahip etki alanı sınıfları tarafından kullanıcı durumunu ve bir kısmının modeldeki toplam öğeleri olarak bu sayısını temsil eden bir dize döndürür.  
  
 Ayrıca, depolama ve alma ve ayarlama, Namespace özel depolama özelliği için yöntemleri eklemek `ExampleElement` etki alanı sınıfı.  
  
> [!NOTE]
>  İçin DSL araçları üret kod `ExampleModel` get çağrıları ve set yöntemlerini; ancak, DSL araçları yöntemlerini uygulayan kod oluşturmaz.  
  
#### <a name="to-add-the-method-for-the-custom-type-descriptor"></a>Özel tür açıklayıcı yöntemi eklemek için  
  
1.  NamespaceTrackingProperty.cs dosyasına aşağıdaki kodu ekleyin.  
  
    ```csharp  
    using System;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        // To the domain class that has the tracking property, add the caluclation  
        // for when the property is tracking.  
        public partial class ExampleElement  
        {  
            /// <summary>Calculates the actual value of the property when it is  
            /// tracking.</summary>  
            /// <returns>The value of the tracking property when it is  
            /// tracking.</returns>  
            /// <remarks>Making this method virtual allows child classes to modify  
            /// the calculation. This method does not need to perform validation, as  
            /// its caller handles validation prior to calling this method.  
            /// <para>In this case, the tracking value depends on the default namespace  
            /// property of the parent model.</para></remarks>  
            protected virtual string CalculateNamespace()  
            {  
                return this.ExampleModel.DefaultNamespace;  
            }  
  
            #region Tracking property implementation  
  
            // Implement the Namespace domain property of the ExampleElement domain class,  
            // and update the IsNamespaceTracking domain property value handler.  
  
            /// <summary>Storage for the Namespace property.</summary>  
            private string namespaceStorage;  
  
            /// <summary>Gets the value of the Namespace property.</summary>  
            /// <returns>The value of the Namespace property.</returns>  
            private string GetNamespaceValue()  
            {  
                // Only retrieve the tracked value if the store is not in the  
                // middle of a serialization transaction.  
                bool loading = this.Store.TransactionManager.InTransaction  
                    && this.Store.TransactionManager.CurrentTransaction.IsSerializing;  
  
                if (!loading && this.IsNamespaceTracking)  
                {  
                    try  
                    {  
                        return this.CalculateNamespace();  
                    }  
                    catch (NullReferenceException)  
                    {  
                        return default(string);  
                    }  
                    catch (Exception e)  
                    {  
                        if (CriticalException.IsCriticalException(e))  
                        {  
                            throw;  
                        }  
                        else  
                        {  
                            return default(string);  
                        }  
                    }  
                }  
  
                return namespaceStorage;  
            }  
  
            /// <summary>Sets the value of the Namespace property.</summary>  
            /// <param name="value">The new value for the property.</param>  
            private void SetNamespaceValue(string value)  
            {  
                namespaceStorage = value;  
  
                // Only update the state of the tracking property if the store is  
                // not in the middle of a serialization transaction.  
                bool loading = this.Store.TransactionManager.InTransaction  
                    && this.Store.TransactionManager.CurrentTransaction.IsSerializing;  
  
                if (!this.Store.InUndoRedoOrRollback && !loading)  
                {  
                    this.IsNamespaceTracking = false;  
                }  
            }  
  
            // Update the default behavior of the ExampleElement.IsNamespaceTracking  
            // domain property value handler.  
            internal sealed partial class IsNamespaceTrackingPropertyHandler  
            {  
                /// <summary>Called after the IsNamespaceTracking property changes.  
                /// </summary>  
                /// <param name="element">The model element that has the property  
                /// that changed.</param>  
                /// <param name="oldValue">The previous value of the property.  
                /// </param>  
                /// <param name="newValue">The new value of the property.</param>  
                protected override void OnValueChanged(  
                    ExampleElement element, Boolean oldValue, Boolean newValue)  
                {  
                    base.OnValueChanged(element, oldValue, newValue);  
                    if (!element.Store.InUndoRedoOrRollback && newValue)  
                    {  
                        DomainPropertyInfo propInfo =  
                            element.Store.DomainDataDirectory.GetDomainProperty(  
                                ExampleElement.NamespaceDomainPropertyId);  
                        propInfo.NotifyValueChange(element);  
                    }  
                }  
  
                /// <summary>Performs the reset operation for the IsNamespaceTracking  
                /// property for a model element.</summary>  
                /// <param name="element">The model element that has the property  
                /// to reset.</param>  
                internal void ResetValue(ExampleElement element)  
                {  
                    object calculatedValue = null;  
  
                    try  
                    {  
                        calculatedValue = element.CalculateNamespace();  
                    }  
                    catch (NullReferenceException)  
                    {  
                    }  
                    catch (System.Exception e)  
                    {  
                        if (CriticalException.IsCriticalException(e))  
                        {  
                            throw;  
                        }  
                    }  
  
                    if ((calculatedValue != null  
                        && object.Equals(element.Namespace, calculatedValue)))  
                    {  
                        element.isNamespaceTrackingPropertyStorage = true;  
                    }  
                }  
  
                /// <summary>Method to set IsNamespaceTracking to false so that this  
                /// instance of this tracking property is not storage-based.  
                /// </summary>  
                /// <param name="element">The element on which to reset the property  
                /// value.</param>  
                internal void PreResetValue(ExampleElement element)  
                {  
                    // Force the IsNamespaceTracking property to false so that the value  
                    // of the Namespace property is retrieved from storage.  
                    element.isNamespaceTrackingPropertyStorage = false;  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
## <a name="adding-custom-code-to-support-serialization"></a>Seri hale getirme desteklemek için özel kod ekleme  
 XML serileştirme için özel sonrası yük davranışını desteklemek için kodu ekleyin.  
  
> [!NOTE]
>  Kod DSL araçları çağrıları üret `OnPostLoadModel` ve `OnPostLoadModelAndDiagram` yöntemleri; ancak, bu yöntemleri uygulayan kod DSL araçları oluşturmaz.  
  
#### <a name="to-add-code-to-support-the-custom-post-load-behavior"></a>Özel sonrası yük davranışını desteklemek üzere kod eklemek için  
  
1.  Serialization.cs dosyasına aşağıdaki kodu ekleyin.  
  
    ```csharp  
    using System;  
    using System.Diagnostics;  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace CompanyName.ProductName.TrackingPropertyDSL  
    {  
        #region Helper classes for maintaining state while the store is serializing.  
  
        public abstract partial class TrackingPropertyDSLSerializationHelperBase  
        {  
            /// <summary>Reset the tracking state properties to their natural values  
            /// based on comparing storage with calculation.</summary>  
            /// <param name="store">The store that contains this model.</param>  
            internal static void ResetTrackingProperties(Store store)  
            {  
                // Two passes required - one to set all elements to storage-based  
                // then another to set some back to being tracking.  
                foreach (ModelElement element in store.ElementDirectory.AllElements)  
                {  
                    ExampleElement myElementInstance = element as ExampleElement;  
                    if (myElementInstance != null)  
                    {  
                        myElementInstance.PreResetIsTrackingProperties();  
                        continue;  
                    }  
                }  
                foreach (ModelElement element in store.ElementDirectory.AllElements)  
                {  
                    ExampleElement myElementInstance = element as ExampleElement;  
                    if (myElementInstance != null)  
                    {  
                        myElementInstance.ResetIsTrackingProperties();  
                        continue;  
                    }  
                }  
            }  
        }  
  
        // Add the pre-reset and reset methods for the model element.  
        public partial class ExampleElement  
        {  
            /// <summary>Calls the pre-reset method on the associated property value  
            /// handler for each tracking property of this model element.</summary>  
            internal virtual void PreResetIsTrackingProperties()  
            {  
                ExampleElement.IsNamespaceTrackingPropertyHandler.Instance.PreResetValue(this);  
            }  
  
            /// <summary>Calls the reset method on the associated property value  
            /// handler for each tracking property of this model element.</summary>  
            internal virtual void ResetIsTrackingProperties()  
            {  
                ExampleElement.IsNamespaceTrackingPropertyHandler.Instance.ResetValue(this);  
            }  
        }  
  
        #endregion  
  
        #region Custom serialization code  
  
        // To the serialization helper for the TrackingPropertyDSL class, add post  
        // load handlers to bind the tracking property to the serialization process.  
        // These handlers manage the tracking states and property values when the  
        // model is serialized and deserialized.  
        public partial class TrackingPropertyDSLSerializationHelperBase  
        {  
            /// <summary>Customize model loading.</summary>  
            /// <param name="serializationResult">The serialization result from the  
            /// load operation.</param>  
            /// <param name="partition">The partition in which the new  
            /// instance was created.</param>  
            /// <param name="fileName">The name of the file from which the  
            /// instance was deserialized.</param>  
            /// <param name="modelRoot">The root of the file that was loaded.  
            /// </param>  
            private void OnPostLoadModel(  
                SerializationResult serializationResult,  
                Partition partition,  
                string fileName,  
                ExampleModel modelRoot)  
            {  
            }  
  
            /// <summary>Customize model and diagram loading.</summary>  
            /// <param name="serializationResult">Stores serialization result from  
            /// the load operation.</param>  
            /// <param name="modelPartition">Partition in which the new  
            /// instance will be created.</param>  
            /// <param name="modelFileName">Name of the file from which the  
            /// instance will be deserialized.</param>  
            /// <param name="diagramPartition">Partition in which the new  
            /// diagram instance will be created.</param>  
            /// <param name="diagramFileName">Name of the file from which the  
            /// diagram instance will be deserialized.</param>  
            /// <param name="modelRoot">The root of the file that was loaded.</param>  
            /// <param name="diagram">The diagram matching the modelRoot.</param>  
            private void OnPostLoadModelAndDiagram(  
                SerializationResult serializationResult,  
                Partition modelPartition,  
                string modelFileName,  
                Partition diagramPartition,  
                string diagramFileName,  
                ExampleModel modelRoot,  
                TrackingPropertyDSLDiagram diagram)  
            {  
                Debug.Assert(modelPartition != null);  
                Debug.Assert(modelPartition.Store != null);  
  
                // Tracking properties need to be set up according to whether the  
                // serialization matches the calculated values.  
                TrackingPropertyDSLSerializationHelperBase.ResetTrackingProperties(  
                    modelPartition.Store);  
            }  
        }  
  
        #endregion  
    }  
    ```  
  
## <a name="testing-the-language"></a>Dil test etme  
 Derleme ve yeni bir örneğini içinde DSL Tasarımcısı'nı çalıştırmak için sonraki adımdır [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] böylece izleme özelliği düzgün çalıştığını doğrulayabilirsiniz.  
  
#### <a name="to-exercise-the-language"></a>Dil uygulamak için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **çözümü yeniden derle**.  
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
     Deneysel yapısını [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] açılır **hata ayıklama** boş test dosyasını içeren çözümü.  
  
3.  İçinde **Çözüm Gezgini**Tasarımcısı'nda açmak için Test.trackingPropertyDsl dosyasını çift tıklatın ve tasarım yüzeyine'ye tıklayın.  
  
     İçinde dikkat **özellikleri** penceresi diyagramı için **varsayılan Namespace** özelliği **DefaultNamespace**ve **özel öğeleri** özelliği **0/0**.  
  
4.  Sürükleme bir **ExampleElement** öğesinden **araç** diyagramı yüzeyine.  
  
5.  İçinde **özellikleri** pencere öğesinin, select **öğesi Namespace** özelliği ve değerini değiştirmek **DefaultNamespace** için  **OtherNamespace**.  
  
     Dikkat değerini **öğesi Namespace** şimdi kalın olarak gösterilir.  
  
6.  İçinde **özellikleri** penceresinde sağ **öğesi Namespace**ve ardından **sıfırlama**.  
  
     Özelliğinin değeri olarak değiştirilmesini **DefaultNamespace**, ve değer normal bir yazı tipinde gösterilir.  
  
     Sağ **öğesi Namespace** yeniden. **Sıfırlama** komutu artık devre dışı özelliği şu anda kendi izleme durumunda olduğundan.  
  
7.  Başka bir sürükleyin **ExampleElement** gelen **araç** diyagram yüzeyine ve değişiklik kendi **öğesi Namespace** için **OtherNamespace**.  
  
8.  Tasarım yüzeyine'ı tıklatın.  
  
     İçinde **özellikleri** değerini diyagramı penceresi **özel öğeleri** artık **1/2**.  
  
9. Değişiklik **varsayılan Namespace** diyagramdan için **DefaultNamespace** için **NewNamespace**.  
  
     **Namespace** ilk öğesi parçalarının **varsayılan Namespace** özelliği, ancak **Namespace** saniyesi öğesi kendi kullanıcı güncelleştirilmiş değerinikorur. **OtherNamespace**.  
  
10. Çözüm kaydedin ve ardından deneysel yapı kapatın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Birden fazla izleme özelliğini kullanın veya içinde birden fazla DSL izleme özellikleri uygulamak düşünüyorsanız, her izleme özelliğini desteklemek için ortak kodu oluşturmak için bir metin şablonu oluşturabilirsiniz. Metin şablonları hakkında daha fazla bilgi için bkz: [kod oluşturma ve T4 metin şablonları](../modeling/code-generation-and-t4-text-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Modeling.Design.TrackingPropertyDescriptor>   
 <xref:Microsoft.VisualStudio.Modeling.Design.ElementTypeDescriptor>   
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)   
 [Nasıl yapılır: Etki Alanına Özgü Dil Çözümü Oluşturma](../modeling/how-to-create-a-domain-specific-language-solution.md)   

---
title: Düzenleyicisi'nde Genişletilebilirlik Çerçevesi yönetilen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - using MEF for extensions
ms.assetid: 3f59a285-6c33-4ae3-a4fb-ec1f5aa21bd1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 91b507893cf2d17b9885944a766c9c9a8c084a7a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="managed-extensibility-framework-in-the-editor"></a>Düzenleyicideki Yönetilen Genişletilebilirlik Çerçevesi
Düzenleyici, Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşenlerini kullanarak oluşturulmuştur. Düzenleyiciyi genişletmek için kendi MEF Bileşenleri oluşturabilirsiniz ve kodunuzu Düzenleyicisi bileşenleri kullanmasını sağlayabilirsiniz.  
  
## <a name="overview-of-the-managed-extensibility-framework"></a>Yönetilen Genişletilebilirlik Çerçevesi'ne genel bakış  
 MEF ekleme ve bir uygulama veya MEF programlama modeli izleyen bileşen özelliklerini değiştirme olanak sağlayan bir .NET kitaplıktır. Visual Studio düzenleyicisinde sağlamak hem MEF Bileşeni bölümleri kullanabilir.  
  
 MEF .NET Framework sürüm 4 System.ComponentModel.Composition.dll bütünleştirilmiş kodunda yer alır.  
  
 MEF hakkında daha fazla bilgi için bkz: [Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index).  
  
### <a name="component-parts-and-composition-containers"></a>Bileşen parçalarını ve bileşim kapsayıcılar  
 Bir sınıf veya bir (veya her ikisi de) aşağıdakileri yapmak için bir sınıf üyesi bir bileşen bir parçasıdır:  
  
-   Başka bir bileşen kullanma  
  
-   Başka bir bileşen tarafından tüketilen  
  
 Örneğin, ürün kullanılabilirlik veri ambarı Envanter bileşeni tarafından sağlanan bağımlı bir sipariş girişi bileşen olan bir alışveriş uygulama göz önünde bulundurun. MEF bağlamında stok bölümü olabilir *verme* ürün kullanılabilirlik verileri ve sipariş giriş bölümü can *alma* verileri. Sipariş girişi ve stok bölümlerini diğer hakkında bilmek zorunda değildir; *kapsayıcının* (konak uygulama tarafından sağlanan) dışarı kümesini koruma ve dışarı aktarma çözme sorumludur ve alır.  
  
 Kapsayıcının <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, genellikle ana bilgisayar tarafından sahiplenildi. Kapsayıcının tutan bir *katalog* dışarı aktarılan bileşen bölümlerinin.  
  
### <a name="exporting-and-importing-component-parts"></a>Bileşen bölümleri alma ve verme  
 Ortak bir sınıf veya genel bir sınıf (özellik veya yöntem) üyesi uygulanan sürece herhangi bir işlevsellik dışarı aktarabilirsiniz. Bileşen Bölümü'nden türetilen gerekmez <xref:System.ComponentModel.Composition.Primitives.ComposablePart>. Bunun yerine, eklemelisiniz bir <xref:System.ComponentModel.Composition.ExportAttribute> özniteliği sınıf veya dışarı aktarmak istediğiniz sınıf üyesi. Bu öznitelik belirtir *sözleşme* hangi başka bir bileşen tarafından bölümü, işlev içeri aktarabilirsiniz.  
  
### <a name="the-export-contract"></a>Dışarı aktarma sözleşme  
 <xref:System.ComponentModel.Composition.ExportAttribute> Dışarı aktarılan varlık (sınıf, arabirim veya yapı) tanımlar. Genellikle, dışarı aktarma özniteliği verme türünü belirtir. bir parametre alır.  
  
```  
[Export(typeof(ContentTypeDefinition))]  
class TestContentTypeDefinition : ContentTypeDefinition {   }  
```  
  
 Varsayılan olarak, <xref:System.ComponentModel.Composition.ExportAttribute> özniteliği verme sınıfın türü bir sözleşme tanımlar.  
  
```  
[Export]  
[Name("Structure")]  
[Order(After = "Selection", Before = "Text")]  
class TestAdornmentLayerDefinition : AdornmentLayerDefinition {   }  
```  
  
 Örnekte, varsayılan `[Export]` özniteliği eşdeğerdir `[Export(typeof(TestAdornmentLayerDefinition))]`.  
  
 Ayrıca bir özelliği veya yöntemi, aşağıdaki örnekte gösterildiği gibi aktarabilirsiniz.  
  
```  
[Export]  
[Name("Scarlet")]  
[Order(After = "Selection", Before = "Text")]  
public AdornmentLayerDefinition scarletLayerDefinition;  
```  
  
### <a name="importing-a-mef-export"></a>Bir MEF Export içeri aktarma  
 Bir MEF export kullanmak istediğinizde, dışarı aktarılan ve ekleme Sözleşme (genellikle türü) bilmelisiniz bir <xref:System.ComponentModel.Composition.ImportAttribute> bu değerine sahip öznitelik. Varsayılan olarak, Import özniteliği değiştirdiği sınıfı türünde bir parametre alır. Kod içeri aktarma aşağıdaki satırları <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService> türü.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationRegistry;  
```  
  
## <a name="getting-editor-functionality-from-a-mef-component-part"></a>Bir MEF Bileşeni bölümünden Düzenleyicisi işlevselliği alma  
 Mevcut kodunuzu bir MEF bileşen parçası ise, düzenleyici bileşen bölümü kullanmak için MEF meta verileri kullanabilirsiniz.  
  
#### <a name="to-consume-editor-functionality-from-a-mef-component-part"></a>Bir MEF Bileşeni bölümünden Düzenleyicisi işlevselliği kullanmak için  
  
1.  Genel derleme önbelleğinde (GAC) olduğunu, System.Composition.ComponentModel.dll ve düzenleyici derlemeler için başvurular ekleyin.  
  
2.  İlgili eklemek using deyimleri.  
  
    ```  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text;  
    ```  
  
3.  Ekleme `[Import]` hizmet arabiriminiz için aşağıdaki gibi özniteliği.  
  
    ```  
    [Import]  
    ITextBufferFactoryService textBufferService;  
    ```  
  
4.  Hizmet aldığınızda bileşenlerinden herhangi birini kullanabilir.  
  
5.  Ne zaman, derlenmiş bunu koymak derlemenizi... Visual Studio yüklemenizin \Common7\IDE\Components\ klasör.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)
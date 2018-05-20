---
title: Özel XML bölümlerine genel bakış
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom XML parts [Office development in Visual Studio], about
- Office Open XML Formats [Office development in Visual Studio]
- custom XML parts [Office development in Visual Studio]
- embedding XML data in documents [Office development in Visual Studio]
- XML parts [Office development in Visual Studio]
- XML file formats [Office development in Visual Studio]
- data [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- XML [Office development in Visual Studio], custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- documents [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e99e64de135ab46baf40a959986c041538c09593
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="custom-xml-parts-overview"></a>Özel XML bölümlerine genel bakış
  Bazı Microsoft Office uygulamaları için belgelerde XML verileri eklenebilir. XML verilerini bir belgede katıştırma veriler adlı bir *özel XML parçaları*.  
  
 Oluşturma ve VSTO eklentisi kullanarak özel XML bölümleri belgede değiştirme veya belge düzeyi Visual Studio'da çözüm. Oluşturup özel XML bölümleri değiştirmek için Microsoft Office uygulamayı başlatmak gerekmez.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Excel, PowerPoint ve Word için belge düzeyi projelerine ve VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
> [!NOTE]  
>  Visual Studio ayrıca belge düzeyi özelleştirmelerinde veri nesneleri önbelleğe almak için sağlar. Bazı benzerlikler olsa bu özel XML bölümleri, farklı bir özelliktir. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmelerinde verileri önbelleğe](../vsto/cached-data-in-document-level-customizations.md).  
  
## <a name="understand-custom-xml-parts"></a>Özel XML bölümleri anlama  
 Özel XML bölümleri 2007 Microsoft Office sistemi açık XML Biçimleri birlikte tanıtıldı. Bu yeni dosya XML tabanlı biçimler Excel, PowerPoint ve Word için biçimler (gibi *.xlsx*, *.pptx*, ve *.docx*). Bu biçimlerdeki belgeler oluşur XML dosyalarını (olarak da adlandırılan *XML bölümleri*) ZIP arşivindeki klasörlerde düzenlenir. XML bölümlerinin yapısı ve belgenin durumunu tanımlamanıza yardımcı olur yerleşik bölümleri durumdadır. Bununla birlikte, belgeleri de belgelerde rasgele XML verilerini depolamak için kullanabileceğiniz özel XML bölümleri içerebilir.  
  
 Eski ikili dosya biçimleriyle mümkün olmayan yollarla belgelerle çalışmak üzere etkinleştir uygulamaları XML dosya biçimleri (gibi *.xls*, *.ppt*, ve *.doc*). ZIP arşivini okuyabilir herhangi bir uygulama inceleyin ve Microsoft Office yüklü olmasa bile belge içeriklerini değiştirin.  
  
 Open XML ve özel XML bölümleri yapısı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
-   [Office (2007) açık XML dosya biçimleri](http://msdn.microsoft.com/en-us/96018532-f62c-4da7-bbff-16b96a483fbf)  
  
-   [Nasıl yapılır: Açık XML Biçimleri belgelerini değiştirme](http://msdn.microsoft.com/en-us/c989d4e2-053d-4e1f-83be-257c608b343f)  
  
-   [İzlenecek yol: Word 2007 XML biçimi](http://msdn.microsoft.com/en-us/fc1afcb2-27fb-4608-9f29-11b7bd23ea4a)  
  
-   [Açık XML biçimleri kullanarak Word 2007 belgeleri oluşturma](http://msdn.microsoft.com/en-us/59a46f4e-5a5a-4dac-86e5-7dfd43330766)  
  
> [!NOTE]  
>  Ayrıca Excel, Word ve PowerPoint ikili dosya biçimlerinde kaydedilir belgelerde özel XML bölümleri kullanmanıza olanak sağlar. Ancak, ikili biçimde bir belge kaydettiyseniz, ekleyemez veya Microsoft Office uygulamasını başlatmadan özel XML bölümleri değiştirmek.  
  
## <a name="create-and-modify-custom-xml-parts"></a>Oluşturma ve değiştirme özel XML bölümleri  
 Oluşturabilir veya özel XML bölümleri belgeyi Office uygulamasında açık olduğunda veya belge kapatıldığında değiştirmek — Microsoft Office yüklü değilse.  
  
### <a name="modify-xml-parts-while-the-office-application-is-running"></a>Office uygulaması çalışırken XML bölümlerini Değiştir  
 Belge düzeyi özelleştirme veya bir VSTO eklenti kullanarak özel XML bölümleri ile çalışabilirsiniz. Belge düzeyi özelleştirme kullanıyorsanız, genellikle özelleştirilmiş belgedeki özel XML bölümleri ile çalışır. Bir VSTO eklenti kullanıyorsanız, oluşturmak veya özel XML bölümleri uygulamada açık olan herhangi bir belgede değiştirin.  
  
 Visual Studio kullanarak özel bir XML parçasına oluşturmak için yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> için <xref:Microsoft.Office.Core.CustomXMLParts> belge koleksiyonu. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: belge düzeyi özelleştirmelerine özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
-   [Nasıl yapılır: VSTO eklentileri kullanarak belgelere özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  
### <a name="modify-xml-parts-without-starting-the-office-application"></a>Office uygulaması başlatmadan XML bölümlerini Değiştir  
 Ekleyin veya özel bir XML parçasına Excel, PowerPoint ve Word başlatmadan değiştirin. Microsoft Office uygulamaları, bir sunucu gibi yüklü olmayan bir bilgisayarda bir belgedeki XML verileri çalışmak istiyorsanız kullanışlıdır.  
  
 Microsoft Office'i başlatmadan özel bir XML parçasına eklemek için Açık XML SDK'ın sınıflarını kullanın. Bu sınıfları, Office belgeleri için belirli Open XML içeriğine erişim sağlamak için tasarlanmıştır. Örneğin, bir Excel çalışma kitabı için özel bir XML parçasına eklemek için kullandığınız [WorkbookPart\<T >](http://msdn.microsoft.com/en-us/47c348c0-77ab-a504-5097-bcd6a213921a) yöntemi bir [AddNewPart](http://msdn.microsoft.com/en-us/d011e6f4-77dd-d02d-66ef-dc4a9e7b26f2) nesnesi. Daha fazla bilgi için bkz: [açık XML SDK 2.0](http://msdn.microsoft.com/en-us/f6a9ae68-7989-4208-97f5-3c945137a0ab).  
  
## <a name="bind-custom-xml-parts-to-word-content-controls"></a>Özel XML bölümleri Word içerik denetimlerine bağlama  
 Word çözümündeki içerik denetimlerini özel bir XML parçasına öğeleri bağlayabilirsiniz. İçerik denetimi için özel bir XML parçasına bağlı olduğunda özel XML parçaları verilerde içerik denetimi kullanıcı arabiriminde (UI) görüntülenir. Bir kullanıcı denetimi metin düzenlemeleri, karşılık gelen XML öğesi otomatik olarak güncelleştirilir. Benzer şekilde, özel XML bölümleri öğesi değerleri değiştirdiyseniz, XML öğelerine bağlanmış içerik denetimleri yeni verileri görüntüler. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [XML şemaları ve verileri belge düzeyi özelleştirmeleri](../vsto/xml-schemas-and-data-in-document-level-customizations.md)   
 [Nasıl yapılır: belge düzeyi özelleştirmelerine özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)   
 [Nasıl yapılır: VSTO eklentileri kullanarak belgelere özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)   
 [İçerik denetimleri](../vsto/content-controls.md)   
 [İzlenecek yol: içerik denetimlerini özel XML bölümlerine bağlama](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)  
  
  
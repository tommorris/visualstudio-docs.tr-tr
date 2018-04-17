---
title: 'İzlenecek yol: İçerik denetimlerini özel XML bölümlerine bağlama | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- PlainTextContentControl, binding to a custom XML part
- custom XML parts, binding to content controls
- content controls [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], content controls
- DropDownListContentControl, binding items to a custom XML part
- DatePickerContentControl, binding to a custom XML part
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ca9c3e049d29874419327ec4ac7d71e0537466c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-binding-content-controls-to-custom-xml-parts"></a>İzlenecek Yol: İçerik Denetimlerini Özel XML Bölümlerine Bağlama
  Bu kılavuz, Word için belge düzeyi özelleştirmelerinde içerik denetimlerini belgede depolanan XML veri bağlamak gösterilmiştir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word adlı XML verileri depolamak sağlar *özel XML bölümleri*, belgede. İçerik denetimleri özel bir XML parçasına öğeleri bağlama tarafından bu verilerin görünümünü denetleyebilirsiniz. Bu kılavuzda örnek belge özel bir XML parçasına içinde depolanan çalışan bilgilerini görüntüler. Belgeyi açtığında, içerik denetimleri XML öğelerinin değerlerini görüntüler. İçerik denetimleri metinde yaptığınız tüm değişiklikler özel XML bölümünde kaydedilir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Tasarım zamanında bir belge düzeyi projede Word belgesine içerik denetimleri ekleme.  
  
-   XML veri dosyası ve içerik denetimlerine bağlama öğeleri tanımlayan bir XML şeması oluşturma.  
  
-   XML Şeması belgeye tasarım zamanında ekleniyor.  
  
-   XML dosyasının içeriğini belgedeki özel bir XML parçasına çalışma zamanında ekleme.  
  
-   İçerik denetimlerini özel XML parçasına öğeleri bağlama.  
  
-   Bağlama bir <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> bir XML Şeması'nda tanımlanan değerleri kümesi için.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word.  
  
## <a name="creating-a-new-word-document-project"></a>Yeni bir Word belgesi projesi oluşturma  
 Kullanacağınız bir Word belgesi kılavuzda oluşturun.  
  
#### <a name="to-create-a-new-word-document-project"></a>Yeni bir Word belgesi projesi oluşturmak için  
  
1.  Adlı bir Word belgesi projesi oluşturun **ÇalışanDenetimleri**. Çözüm için yeni bir belge oluşturun. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tasarımcıda yeni Word belgesini açar ve ekler **ÇalışanDenetimleri** için proje **Çözüm Gezgini**.  
  
## <a name="adding-content-controls-to-the-document"></a>Belgeye içerik denetimleri ekleme  
 Burada kullanıcının görüntüleyebilir veya bir çalışan hakkındaki bilgileri düzenleyebilirsiniz içerik denetimleri üç farklı türde içeren bir tablo oluşturun.  
  
#### <a name="to-add-content-controls-to-the-document"></a>İçerik denetimleri belgeye eklemek için  
  
1.  İçinde barındırılan Word belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Şerit üzerindeki Tasarımcısı'nı seçin **Ekle** sekmesi.  
  
2.  İçinde **tabloları** grubunda, seçin **tablo**ve 2 ve 3 sütun içeren bir tablo ekleyin.  
  
3.  Böylece aşağıdaki sütunun benzer ilk sütunda metni yazın:  
  
    ||  
    |-|  
    |**Çalışan adı**|  
    |**İşe alma tarihi**|  
    |**Başlık**|  
  
4.  Tablonun ikinci sütunda ilk satırını seçin (yanına **çalışan adı**).  
  
5.  Şerit'te seçin **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
6.  İçinde **denetimleri** grubunda, seçin **metin** düğmesini ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>ilk hücrenin.  
  
7.  İkinci satır tablonun ikinci sütunda seçin (yanına **işe alma tarihi**).  
  
8.  İçinde **denetimleri** grubunda, seçin **tarih seçici** düğmesini ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.DatePickerContentControl> ikinci hücreye.  
  
9. Üçüncü satır tablonun ikinci sütunda seçin (yanına **başlık**).  
  
10. İçinde **denetimleri** grubunda, seçin **aşağı açılan liste** düğmesini ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") eklemek için bir <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> son hücreye.  
  
 Bu proje için tüm kullanıcı arabirimi olmasıdır. Şimdi, proje çalıştırırsanız ilk satırda bir metin yazın ve ikinci satırda bir tarih seçin. Sonraki adım, bir XML dosyası belgeye görüntülemek istediğiniz verileri eklemektir.  
  
## <a name="creating-the-xml-data-file"></a>XML veri dosyası oluşturma  
 Genellikle, bir dosya veya veritabanı gibi bir dış kaynaktan özel bir XML parçasına depolamak için XML verileri alacaktır. Bu kılavuzda, belgedeki içerik denetimlerine bağlama öğeleri tarafından işaretlenen çalışan verilerini içeren bir XML dosyası oluşturun. Çalışma zamanında verileri kullanılabilir duruma getirmek için XML dosyasını bir kaynak olarak özelleştirme derlemede katıştırmak.  
  
#### <a name="to-create-the-data-file"></a>Veri dosyası oluşturmak için  
  
1.  Üzerinde **proje** menüsünde seçin **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.  
  
2.  İçinde **şablonları** bölmesinde, **XML dosyası**.  
  
3.  Dosya adı **employees.xml**ve ardından **Ekle** düğmesi.  
  
     **Employees.xml** dosyasını Kod Düzenleyicisi'nde açar.  
  
4.  Değiştir **employees.xml** aşağıdaki metinle dosya.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
      <employee>  
        <name>Karina Leal</name>  
        <hireDate>1999-04-01</hireDate>  
        <title>Manager</title>  
      </employee>  
    </employees>  
    ```  
  
5.  İçinde **Çözüm Gezgini**, seçin **employees.xml** dosya.  
  
6.  İçinde **özellikleri** penceresinde, seçin **yapı eylemi** özelliği ve değerini değiştirin **katıştırılmış kaynak**.  
  
     Projeyi derlerken bu adımı bütünleştirilmiş kodunda bir kaynak olarak XML dosyasını katıştırır. Bu, çalışma zamanında XML dosyasının içeriğini erişmenize olanak tanır.  
  
## <a name="creating-an-xml-schema"></a>Bir XML şeması oluşturma  
 Özel bir XML parçasına tek bir öğede içerik denetimi bağlamak istiyorsanız, bir XML şeması kullanmak zorunda değil. Ancak, bağlamak için <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> değerleri kümesi için daha önce oluşturduğunuz XML veri dosyası doğrulayan bir XML Şeması oluşturmalısınız. XML şeması için olası değerler tanımlar `title` öğesi. Bağlı olacağı <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> bu kılavuzda daha sonra bu öğeye.  
  
#### <a name="to-create-an-xml-schema"></a>Bir XML şeması oluşturmak için  
  
1.  Üzerinde **proje** menüsünde seçin **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.  
  
2.  İçinde **şablonları** bölmesinde, **XML Şeması**.  
  
3.  Şema adı **employees.xsd** ve **Ekle** düğmesi.  
  
     Şema Tasarımcısı'nı açar.  
  
4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **employees.xsd**ve ardından **görünümü kodu**.  
  
5.  Değiştir **employees.xsd** aşağıdaki şema dosyası.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <xs:schema xmlns="http://schemas.microsoft.com/vsto/samples"   
        targetNamespace="http://schemas.microsoft.com/vsto/samples"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema"  
        elementFormDefault="qualified">  
      <xs:element name="employees" type="EmployeesType"></xs:element>  
      <xs:complexType name="EmployeesType">  
        <xs:all>  
          <xs:element name="employee" type="EmployeeType"/>  
        </xs:all>  
      </xs:complexType>  
      <xs:complexType name="EmployeeType">  
        <xs:sequence>  
          <xs:element name="name" type="xs:string" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="hireDate" type="xs:date" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="title" type="TitleType" minOccurs="1" maxOccurs="1"/>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:simpleType name="TitleType">  
        <xs:restriction base="xs:string">  
          <xs:enumeration value ="Engineer"/>  
          <xs:enumeration value ="Designer"/>  
          <xs:enumeration value ="Manager"/>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:schema>  
    ```  
  
6.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** yaptığınız değişiklikleri kaydetmek için **employees.xml** ve **employees.xsd** dosyaları.  
  
## <a name="attaching-the-xml-schema-to-the-document"></a>XML Şeması belgeye ekleme  
 XML Şeması bağlamak için belgeye eklemelisiniz <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> geçerli değerlerine `title` öğesi.  
  
#### <a name="to-attach-the-xml-schema-to-the-document-includeword15shortvstoincludesword-15-short-mdmd"></a>XML Şeması belgeye ([!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)])  
  
1.  Etkinleştirme **ÇalışanDenetimleri.docx'i** Tasarımcısı'nda.  
  
2.  Şerit'te seçin **Geliştirici** sekmesini ve ardından **eklentileri** düğmesi.  
  
3.  İçinde **şablonları ve eklentiler** iletişim kutusunda, seçin **XML Şeması** sekmesini ve ardından **Şema Ekle** düğmesi.  
  
4.  Gözat **employees.xsd** şema daha önce oluşturduğunuz, hangi proje dizininde bulunur ve ardından **açık** düğmesi.  
  
5.  Seçin **Tamam** düğmesini **şema ayarları** iletişim kutusu.  
  
6.  Seçin **Tamam** kapatmak için düğmesini **şablonları ve eklentiler** iletişim kutusu.  
  
#### <a name="to-attach-the-xml-schema-to-the-document-word-2010"></a>XML Şeması (Word 2010) belgeye eklemek için  
  
1.  Etkinleştirme **ÇalışanDenetimleri.docx'i** Tasarımcısı'nda.  
  
2.  Şerit'te seçin **Geliştirici** sekmesi.  
  
3.  İçinde **XML** grubunda, seçin **şema** düğmesi.  
  
4.  İçinde **şablonları ve eklentiler** iletişim kutusunda, seçin **XML Şeması** sekmesini ve ardından **Şema Ekle** düğmesi.  
  
5.  Gözat **employees.xsd** proje dizininde bulunur ve seçin, daha önce oluşturduğunuz şema **açık** düğmesi.  
  
6.  Seçin **Tamam** düğmesini **şema ayarları** iletişim kutusu.  
  
7.  Seçin **Tamam** kapatmak için düğmesini **şablonları ve eklentiler** iletişim kutusu.  
  
     **XML yapısı** görev bölmesi açılır.  
  
8.  Kapat **XML yapısı** görev bölmesi.  
  
## <a name="adding-a-custom-xml-part-to-the-document"></a>Özel XML parçası belgeye ekleme  
 XML dosyasındaki öğelere içerik denetimleri bağlamadan önce yeni bir özel XML bölümüne XML dosyasının içeriğini eklemeniz gerekir.  
  
#### <a name="to-add-a-custom-xml-part-to-the-document"></a>Özel bir XML parçasına belgeye eklemek için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ThisDocument.vb** veya **ThisDocument.vb**ve ardından **görünümü kodu**.  
  
2.  Aşağıdaki bildirimi ekleme `ThisDocument` sınıfı. Bu kod, özel bir XML parçasına belgeye eklemek için kullanacağınız birkaç nesneleri bildirir.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#1)]  
  
3.  Aşağıdaki yöntemi ekleyin `ThisDocument` sınıfı. Bu yöntem, bir kaynak olarak derlemede katıştırılır ve içeriği XML dizesi olarak döndürür XML veri dosyasının içeriğini alır.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#3)]  
  
4.  Aşağıdaki yöntemi ekleyin `ThisDocument` sınıfı. `AddCustomXmlPart` Yöntemi, yönteme geçirilen bir XML dizesini içeren yeni bir özel XML bölümü oluşturur.  
  
     Özel XML bölümü yalnızca bir kez oluşturulur, özel XML yöntemi oluşturur emin olmak için bölümü özel bir XML parçasına IF eşleşen bir GUID ile belgede zaten yok. İsteğe bağlı olarak bu yöntem çağrılır, ilk kez değerini kaydeder <xref:Microsoft.Office.Core._CustomXMLPart.Id%2A> özelliğine `employeeXMLPartID` dize. Değeri `employeeXMLPartID` dize kullanarak bildirildi çünkü belgede kalıcı <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> özniteliği.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#4)]  
  
## <a name="binding-the-content-controls-to-elements-in-the-custom-xml-part"></a>İçerik denetimlerini özel XML parçasına öğeleri bağlama  
 Kullanarak her içerik denetimi özel XML bölümündeki bir öğeye bağlamak **XMLMapping** her içerik denetimi özelliği.  
  
#### <a name="to-bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>İçerik denetimlerini özel XML parçasına öğeleri bağlamak için  
  
1.  Aşağıdaki yöntemi ekleyin `ThisDocument` sınıfı. Bu yöntem, her içerik denetimi özel XML parçaları bir öğedeki bağlar ve tarih görüntüleme biçimi ayarlar <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#5)]  
  
## <a name="running-your-code-when-the-document-is-opened"></a>Bilgisayarınızı kodu belge çalıştıran açılmış  
 Özel XML bölümü oluşturmak ve belge açıldığında özel denetimler verilere bağlayın.  
  
#### <a name="to-run-your-code-when-the-document-is-opened"></a>Belge açıldığında kodunuzu çalıştırmak için  
  
1.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı. Bu kod XML dizesini alır **employees.xml** dosya, XML dizesi yeni bir özel XML bölümüne ekler ve içerik denetimlerini özel XML parçasına öğeleri bağlar.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#2)]  
  
## <a name="testing-the-project"></a>Projeyi test etme  
 Belgeyi açtığında, içerik denetimlerini özel XML bölümünde öğeleri gelen verileri görüntüler. Tıklayabilirsiniz <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> geçerli üç değerden birini seçmek için `title` tanımlanan öğe **employees.xsd** dosya. İçerik denetimleri hiçbirinde veri düzenlerseniz, yeni değerleri belgedeki özel XML bölümüne kaydedilir.  
  
#### <a name="to-test-the-content-controls"></a>İçerik denetimleri sınamak için  
  
1.  Projeyi çalıştırmak için F5 tuşuna basın.  
  
2.  Belge tabloda aşağıdaki tabloda benzediğini doğrulayın. Her ikinci sütundaki dize, belgedeki özel XML bölümündeki bir öğeden alınır.  
  
    |||  
    |-|-|  
    |**Çalışan adı**|**Karina Leal**|  
    |**İşe alma tarihi**|**1 Nisan 1999**|  
    |**Başlık**|**Yöneticisi**|  
  
3.  Hücre sağındaki seçin **çalışan adı** hücre ve farklı bir ad yazın.  
  
4.  Hücre sağındaki seçin **işe alma tarihi** hücre ve tarih seçiciden farklı bir tarih seçin.  
  
5.  Hücre sağındaki seçin **başlık** hücre ve aşağı açılan listeden yeni bir öğe seçin.  
  
6.  Belgesini kaydedin ve kapatın.  
  
7.  Dosya Gezgini'nde projenizin konumunu altındaki \bin\Debug klasörünü açın.  
  
8.  Kısayol menüsünü açın **ÇalışanDenetimleri.docx'i** ve ardından **yeniden adlandırma**.  
  
9. Dosya adı **ÇalışanDenetimleri.docx.zip**.  
  
     **ÇalışanDenetimleri.docx'i** belge Open XML biçiminde kaydedilir. Bu belge .zip dosya adı uzantısına sahip adlandırarak belgesinin içeriğini inceleyebilirsiniz. Open XML hakkında daha fazla bilgi için teknik makalesine bakın [(2007) Office Açık XML dosya biçimleri Tanıtımı](http://msdn.microsoft.com/en-us/96018532-f62c-4da7-bbff-16b96a483fbf).  
  
10. Açık **ÇalışanDenetimleri.docx.zip** dosya.  
  
11. Açık **customXml** klasör.  
  
12. Kısayol menüsünü açın **item2.xml** ve ardından **açık**.  
  
     Bu dosya belgeye eklediğiniz özel XML bölümü içerir.  
  
13. Doğrulayın `name`, `hireDate`, ve `title` öğeler belgedeki içerik denetimlerine girdiğiniz yeni değerleri içerir.  
  
14. Kapat **item2.xml** dosya.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan içerik denetimlerini kullanma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Bir şablon oluşturmak için kullanılabilir tüm içerik denetimlerini kullanın. Daha fazla bilgi için bkz: [izlenecek yol: bir şablon tarafından kullanarak içerik denetimler oluşturma](../vsto/walkthrough-creating-a-template-by-using-content-controls.md).  
  
-   Belge kapalıyken özel XML bölümleri verilerde değiştirin. Kullanıcı belge açıldığında XML öğelerine bağlanmış içerik denetimleri yeni verileri görüntüler.  
  
-   Bir belge parçalarını korumak için içerik denetimleri kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: koruma bölümleri belgeler içerik denetimlerini kullanarak tarafından](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [İçerik denetimleri](../vsto/content-controls.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Nasıl yapılır: içerik denetimlerini kullanarak belge bölümlerini koruma](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Belgelerine Çalışma Zamanında Denetim Ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  
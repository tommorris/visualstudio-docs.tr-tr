---
title: "Nasıl yapılır: XML şemasından bir XML parçacığını oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c128d2a-aaa6-4814-aa95-e07056afe338
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1090d1509152aaa507220d3119977bb8e9252876
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-generate-an-xml-snippet-from-an-xml-schema"></a>Nasıl yapılır: XML şemasından bir XML parçacığını oluştur
XML Düzenleyicisi'ni bir XML Şeması Tanım Dili (XSD) şemadan XML parçacıkları oluşturabilme özelliği vardır. Örneğin, öğe adı yanındaki konumlandırılmış sırada bir XML dosyasına yazma gibi öğenin bu öğe için şema bilgileri üretilen XML verileri ile doldurmak için SEKME tuşuna basabilirsiniz.  
  
 Bu özellik, yalnızca öğeleri üzerinde kullanılabilir. Aşağıdaki kuralları da geçerlidir:  
  
-   Öğe bir ilişkili şema türü olması gerekir; diğer bir deyişle, öğesi ilişkili bazı şemaya göre geçerli olması gerekir. Şema türü soyut olamaz ve türü gerekli öznitelikler içermelidir ve/veya alt öğeleri gerekli.  
  
-   Geçerli öğe Düzenleyicisi'nde özniteliklere boş olmalıdır. Örneğin, tüm geçerli verilmiştir  
  
    -   `<Account`  
  
    -   `<Account>`  
  
    -   `<Account></Account>`  
  
-   İmleç hemen öğe adının sağında yer alması gerekir.  
  
Oluşturulan kod parçacığında, tüm gerekli öznitelikler ve öğeler içerir. Varsa `minOccurs` biri, gerekli en az bu öğenin örnek sayısı en çok 100 örnekleri parçacığı dahil sayısından daha büyük. Herhangi bir kod parçacığını sabit değerleri şema sonucunda bulunan değerleri sabit. `xsd:any`ve `xsd:anyAttribute` öğeleri göz ardı edilir ve hiçbir ek kod parçacığında yapılardan sonucu.  
  
Varsayılan değerler oluşturulan ve düzenlenebilir değerleri olarak kaydedilir. Şema varsayılan bir değer belirtir, bu varsayılan değer kullanılır. Ancak, şema varsayılan değer boş bir dize ise, düzenleyici varsayılan değerleri aşağıdaki şekilde oluşturur:  
  
-   Şema türü herhangi bir sıralama yönü doğrudan veya dolaylı olarak herhangi bir birleşim türü üyeleri yoluyla içeriyorsa, şema nesne modelinde bulunan ilk numaralandırılmış değer varsayılan olarak kullanılır.  
  
-   Şema türü atomik bir tür ise, düzenleyici atomik türünü alır ve atomik tür adı ekler. Türetilen bir basit tür temel basit tür kullanır. Liste türü için atomik türüdür `itemType`. Bir birleşim için atomik türü atomik ilk türdür `memberType`.  
  
## <a name="example"></a>Örnek  
 Bu bölümdeki adımları şema oluşturulan XML parçacığını özelliği XML Düzenleyicisi'nin kullanımını gösterir.  
  
> [!NOTE]
>  Bu yordamlara başlamadan önce şema dosyasını yerel bilgisayarınıza kaydedin.  
  
#### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Yeni bir XML dosyası oluşturmak ve bir XML şeması ile ilişkilendirmek için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**, tıklatıp **dosya**.  
  
2.  Seçin **XML dosyası** içinde **şablonları** bölmesinde ve tıklatın **açık**.  
  
     Yeni bir dosya Düzenleyicisi'nde açılır. Varsayılan XML bildirimi dosyayı içeren `<?xml version="1.0" encoding="utf-8">`.  
  
3.  Belge Özellikleri penceresinde Gözat düğmesine (**...** ) üzerinde **şemaları** alan.  
  
     **XSD şemaları** iletişim kutusu görüntülenir.  
  
4.  **Ekle**'yi tıklatın.  
  
     **Açık XSD şema** iletişim kutusu görüntülenir.  
  
5.  Şema dosyasını seçin ve tıklatın **açık**.  
  
6.  **Tamam**'ı tıklatın.  
  
     XML Şeması sunulmuştur XML belgesi ile ilişkilendirilmiş.  
  
#### <a name="to-generate-an-xml-snippet"></a>Bir XML parçacığını oluşturmak için  
  
1.  Tür `<` Düzenleyicisi bölmesinde.  
  
2.  Üye listesi olası öğeleri görüntüler:  
  
     **!--** bir yorum ekleyin.  
  
     **! DOCTYPE** bir belge türü eklemek için.  
  
     **?** bir işlem yönergesi eklemek için.  
  
     **Kişi** kök öğesi eklemek için.  
  
3.  Seçin **kişi** üye listesi ve ENTER tuşuna basın.  
  
     Düzenleyici başlangıç etiketi ekler `<Contact` ve sonra öğe adı imleci yerleştirir.  
  
4.  XML verileri oluşturmak için SEKME tuşuna basın `Contact` öğesi dayalı, şema bilgileri.  
  
### <a name="input"></a>Giriş  
 Aşağıdaki şema dosyası izlenecek yol tarafından kullanılır.  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema elementFormDefault="qualified"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:simpleType name="phoneType">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Voice"/>  
      <xs:enumeration value="Fax"/>  
      <xs:enumeration value="Pager"/>  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:element name="Contact">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Name">  
          <xs:simpleType>  
            <xs:restriction base="xs:string"></xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
        <xs:element name="Title"  
                    type="xs:string" />  
        <xs:element name="Phone"  
                    minOccurs="1"  
                    maxOccurs="unbounded">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Number"  
                          minOccurs="1">  
                <xs:simpleType>  
                  <xs:restriction base="xs:string"></xs:restriction>  
                </xs:simpleType>  
              </xs:element>  
              <xs:element name="Type"  
                          default="Voice"  
                          minOccurs="1"  
                          type="phoneType"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
### <a name="output"></a>Çıkış  
 Aşağıdadır ilişkili şema bilgileri temel alarak oluşturulan XML veri `Contact` öğesi. İşaretli öğeleri olarak `bold` XML parçacığını düzenlenebilir alanlara belirleyin.  
  
```xml
<Contact>  
  <Name>name</Name>  
  <Title>title</Title>  
  <Phone>  
    <Number>number</Number>  
    <Type>Voice</Type>  
  </Phone>  
</Contact>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML parçacıkları](../xml-tools/xml-snippets.md)   
 [Nasıl yapılır: XML parçacıklarını kullanma](../xml-tools/how-to-use-xml-snippets.md)
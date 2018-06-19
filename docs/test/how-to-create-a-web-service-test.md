---
title: Visual Studio'da Web hizmet testi oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, creating Web service tests
- Web services [Visual Studio ALM], creating
- service tests, Web
ms.assetid: fbcd57ee-06ad-4260-8694-09f8e0f93e39
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2ae66ff032b3f43f80f8c00b12e2d344bba298b9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970710"
---
# <a name="how-to-create-a-web-service-test"></a>Nasıl yapılır: Web Hizmet Testi Oluşturma

Bir Web performans testi için test Web hizmetlerini kullanabilirsiniz. Kullanarak **istek Ekle** ve **Web hizmeti isteği Ekle** seçenekleri, tek tek isteklerinde özelleştirebilirsiniz **Web Performans Testi Düzenleyicisi** Web bulmak için Hizmet sayfaları. Genellikle, bu sayfaları Web uygulamasında görüntülenmez. Bu nedenle, bu sayfaları erişmek için isteği özelleştirmeniz gerekir.

Aşağıdaki yordamlar Commerce Starter Kit içinde yer alan bir Web hizmetini kullanır. Buradan indirebilirsiniz [ASP.NET ticaret Starter Kit](http://go.microsoft.com/fwlink/?LinkId=181469).

 **Gereksinimler**

-   Visual Studio Enterprise

## <a name="to-test-a-web-service"></a>Bir Web hizmeti test etmek için

1.  Yeni bir Web performans testi oluşturun. Tarayıcı açar açmaz seçin **durdurmak**.

2.  İçinde **Web Performans Testi Düzenleyicisi**, Web performans testini sağ tıklatın ve seçin **Web hizmeti isteği Ekle**.

3.  İçinde **Url** yeni istek özelliğinin türü Web hizmeti adı gibi **http://localhost/storecsvs/InstantOrder.asmx**.

4.  Ayrı bir tarayıcı oturumu açın ve .asmx sayfanın URL'sini yazın **adresi** araç. Test ve SOAP iletisi incelemek istediğiniz yöntemi seçin. İçerdiği bir `SOAPAction`.

5.  İçinde **Web Performans Testi Düzenleyicisi**, isteği sağ tıklatın ve seçin **üst bilgi Ekle** yeni bir üstbilgi eklemek için. İçinde **adı** özelliği, türü `SOAPAction`. İçinde **değeri** özelliği, gördüğünüz değeri yazın `SOAPAction`, gibi `"http://tempuri.org/CheckStatus"`.

6.  Düzenleyicideki URL düğümünü genişletin, seçin **dize gövde** düğümü ve **içerik türü** özellik değeri girin `text/xml`.

7.  4. adımda tarayıcıya dönün, Web hizmeti Açıklama sayfasından SOAP isteği XML bölümünü seçin ve panoya kopyalayın.

8.  XML içeriği aşağıdaki örneğe benzer:

     ```xml
     <?xml version="1.0" encoding="utf-8"?>
     <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
     <soap:Body>
       <CheckStatus xmlns="http://tempuri.org/">
         <userName>string</userName>
         <password>string</password>
         <orderID>int</orderID>
       </CheckStatus>
     </soap:Body>
     </soap:Envelope>
     ```

9. Geri dönüp **Web Performans Testi Düzenleyicisi** ve ardından üç nokta (...) içinde **dize gövde** özelliği. Panonun içeriğini özelliğe yapıştırın.

10. Herhangi bir yer tutucu değerlerini XML geçirmek test için geçerli değerlerle değiştirmelisiniz. Önceki örnekte iki örneğini değiştirirler `string` ve bir `int`. Sipariş verdiği bir kayıtlı bir kullanıcı varsa bu Web hizmeti işlemi yalnızca işlemini tamamlar.

11. Web hizmeti isteğine sağ tıklatıp **URL sorgu dizesi parametresi Ekle**.

12. Sorgu dizesi parametresi, bir ad ve değer atayın. Önceki örnekte addır `op` değer `CheckStatus`. Bu Web hizmeti işlemi gerçekleştirmek için tanımlar.

    > [!NOTE]
    > Veri bağlama SOAP gövdesi kullanarak veri bağlama değerleri ile herhangi bir yer tutucu değerini değiştirmek için kullanabileceğiniz `{{DataSourceName.TableName.ColumnName}}` sözdizimi.

13. Testi çalıştırın. Web Performans Testi Sonuçları Görüntüleyicisi'nin üst bölmesinde Web hizmeti isteği seçin. Alt bölmede Web tarayıcısı sekmesini seçin. Web hizmeti ve herhangi bir işlem sonucu tarafından döndürülen XML görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
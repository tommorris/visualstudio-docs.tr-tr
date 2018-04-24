---
title: 'Nasıl Yapılır: Bağlantı Dizelerini Kaydetme ve Düzenleme'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f8ef3a2c-029c-423b-9d9e-a4f1add4f640
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 820808a79c8ed18c08c6c54ba416c0993aac06d5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-save-and-edit-connection-strings"></a>Nasıl Yapılır: Bağlantı Dizelerini Kaydetme ve Düzenleme
Visual Studio uygulama bağlantı dizeleri (uygulama ayarları da bilinir) uygulama yapılandırma dosyasında kaydedilen veya doğrudan uygulamanızda sabit kodlanmış. Uygulama yapılandırma dosyasında bağlantı dizelerini kaydetme uygulamanızı sürdürme görevini basitleştirir. Ardından bağlantı dizesi değiştirilmesi gerekiyorsa, (kaynak kodunda değiştirin ve uygulamayı yeniden derlemenize gerek kalmadan) aksine uygulama ayarları dosyasında güncelleştirebilirsiniz.

Bağlantı dizesi içinde (örneğin, parola) hassas bilgileri depolamak, uygulamanızın güvenliğini etkileyebilir. Uygulama yapılandırma dosyasına kaydedilen bağlantı dizeleri şifrelenmez veya gizlenmiş birisi için dosyaya erişmek ve içeriğini görüntülemek mümkün olabilir. Windows tümleşik güvenliği kullanarak, bir veritabanına erişimi denetlemek için daha güvenli bir yoludur.

Kullanmayı seçmezseniz Windows tümleşik güvenlik ve veritabanınızı bir kullanıcı adı ve parola gerektirir, bağlantı dizesinden atlayabilirsiniz ancak uygulamanız başarıyla veritabanına bağlanmak için bu bilgiyi sağlamanız gerekir. Örneğin, bağlantı dizesi çalışma zamanında dinamik olarak oluşturur ve bu bilgileri kullanıcıya sorar bir iletişim kutusu oluşturabilirsiniz. Bilgileri veritabanına şekilde yakalanırsa güvenlik hala bir sorun olabilir.
Daha fazla bilgi için bkz: [koruma bağlantı bilgilerini](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="to-save-a-connection-string-from-within-the-data-source-configuration-wizard"></a>Veri Kaynağı Yapılandırma Sihirbazı'nı içinde bir bağlantı dizesi kaydetmek için
İçinde **veri kaynağı Yapılandırma Sihirbazı**, bağlantı dizesini Kaydet uygulama yapılandırma dosyası sayfasına bağlantı kaydetmek için bu seçeneği belirleyin.

## <a name="to-save-a-connection-string-directly-into-application-settings"></a>Bir bağlantı dizesi doğrudan uygulama ayarlarını kaydetmek için
- Çözüm Gezgini'nde My proje simgesini (Visual Basic) veya özellikleri simgesini (Proje Tasarımcısı'nı açmak için C#) çift tıklayın.
- Ayarlar sekmesini seçin.
- Bağlantı dizesi için bir ad girin. Bu ad, kodu bağlantı dizesinde erişirken bakın.
- Türü (bağlantı dizesi) olarak ayarlayın.
- Uygulamaya set Scope bırakın.
- Bağlantı dizenizi değer alanına yazın veya bağlantı dizesi oluşturmak için bağlantı özellikleri iletişim kutusunu açmak için değer alanında üç nokta (...) düğmesini tıklatın.

## <a name="editing-connection-strings-stored-in-application-settings"></a>Uygulama ayarları depolanan bağlantı dizeleri düzenleme
Proje Tasarımcısı kullanarak uygulama ayarlarında kaydedilen bağlantı bilgilerini değiştirebilirsiniz.

### <a name="to-edit-a-connection-string-stored-in-application-settings"></a>Uygulama ayarları depolanan bağlantı dizesini düzenlemek için
- Çözüm Gezgini'nde My proje simgesini (Visual Basic) veya özellikleri simgesini (Proje Tasarımcısı'nı açmak için C#) çift tıklayın.
- Ayarlar sekmesini seçin.
- Değer alanına metni seçin ve düzenlemek için istediğiniz bağlantıyı bulun.
- Değer alanı bağlantı dizesinde düzenleyin veya bağlantı özellikleri iletişim kutusu bağlantınızla düzenlemek için değer alanında üç nokta (...) düğmesini tıklatın.

## <a name="editing-connection-strings-for-datasets"></a>Veri kümeleri için bağlantı dizeleri düzenleme
Bir veri kümesinde her TableAdapter bağlantı bilgilerini değiştirebilirsiniz.

### <a name="to-edit-a-connection-string-for-a-tableadapter-in-a-dataset"></a>Bir TableAdapter içinde bir veri kümesi için bir bağlantı dizesini düzenlemek için
- Çözüm Gezgini'nde, düzenlemek istediğiniz bağlantı var. veri kümesi (.xsd dosyası) çift tıklayın.
- TableAdapter veya düzenlemek istediğiniz bağlantısı olan sorguyu seçin.
- Özellikler penceresinde bağlantı düğümünü genişletin.
- Hızlı bir şekilde bağlantı dizesini değiştirmek için ConnectionString özelliğini düzenleyin veya bağlantı özelliği üzerinde bulunan aşağı oku tıklatın ve yeni bir bağlantı seçin.

## <a name="security"></a>Güvenlik
Bağlantı dizesi içinde (örneğin, parola) hassas bilgileri depolamak, uygulamanızın güvenliğini etkileyebilir. Windows tümleşik güvenliği kullanarak, bir veritabanına erişimi denetlemek için daha güvenli bir yoludur.
Daha fazla bilgi için bkz: [koruma bağlantı bilgilerini](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantıları ekleme](../data-tools/add-new-connections.md)
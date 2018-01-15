---
title: "Python Visual Studio için Django web projesi şablonu | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 753c3d78ff3da45213ea7cb9625d765e564a88e1
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="django-web-project-template"></a>Django web proje şablonu

[Django](https://www.djangoproject.com/) hızlı, güvenli ve ölçeklenebilir bir web geliştirme için tasarlanmış bir çerçevedir üst düzey Python. Visual Studio'da Python desteği Django tabanlı web uygulamasının yapıyı ayarlamak için bir proje şablonu sağlar. Visual Studio'da şablonu kullanmak için **Dosya > Yeni > Proje**"Django" için arama yapın ve seçin **Django Web projesi** şablonu. Elde edilen proje, Demirbaş kod varsayılan bir SQLite veritabanı içerir. **Boş Django Web projesi** şablonu benzer, ancak veritabanı dahil değildir.

Visual Studio, Django projeleri için IntelliSense sağlar:

- Bağlam değişkenleri şablonuna geçirildi:

    ![Bağlam değişkenleri için IntelliSense](media/template-django-intellisense.png)

- Etiketleme ve her iki öğelerin filtreleme ve kullanıcı tanımlı:

    ![Etiketleri ve filtreleri için IntelliSense](media/template-django-intellisense-filter.png)

- Katıştırılmış CSS ve JavaScript için renklendirme sözdizimi:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio ayrıca sağlar tam [hata ayıklama desteği](debugging.md) Django projeleri için: 

![Kesme noktaları](media/template-django-debugging.png)

Üzerinden yönetilecek Django projeleri için tipik kendi `manage.py` Visual Studio izleyen varsayılır dosya. Bu dosya giriş noktası olarak kullanarak durdurursanız, aslında proje dosyası bölün. Bu durumda, gerek [var olan dosyaları projeden yeniden](python-projects.md#creating-a-project-from-existing-files) Django projesi olarak işaretleme olmadan.

## <a name="django-management-console"></a>Django Yönetim Konsolu

Django Yönetim Konsolu aracılığıyla çeşitli komutlar üzerinde erişilen **proje** menüsü veya Çözüm Gezgini'nde projeye sağ tıklanarak.

- **Django Kabuğu'nu açın...** : uygulama içeriğiniz Modellerinizi yönetmenize olanak sağlayan bir Kabuğu'nu açar "

    ![Konsol](media/template-django-console-shell.png)

- **Django eşitleme DB**: yürütür `manage.py syncdb` etkileşimli bir pencere olarak:

    ![Konsol](media/template-django-console-sync-db.png)

- **Statik toplamak**: yürütür `manage.py collectstatic --noinput` tarafından belirtilen yol için tüm statik dosyaları kopyalamak için `STATIC_ROOT` içinde `settings.py`. Unutmayın [Microsoft Azure yayımlama](template-web.md#publishing-to-azure-app-service), statik dosyalar, yayımlama işleminin bir parçası olarak otomatik olarak toplanır.

    ![Konsol](media/template-django-console-collect-static.png)

- **Doğrulama**: yürütür `manage.py validate`, tüm doğrulama hatalarını tarafından belirtilen yüklü modellerde raporları `INSTALLED_APPS` içinde `settings.py`:

    ![Konsol](media/template-django-console-validate.png)
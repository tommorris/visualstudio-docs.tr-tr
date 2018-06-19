---
title: Python için Django web proje şablonu
description: Visual Studio şablonları Django framework kullanarak Python içinde yazılmış web uygulamaları için genel bakış.
ms.date: 04/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 077619b7d47441bb4a02dbe87e7cf714b634beff
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031354"
---
# <a name="django-web-project-template"></a>Django web projesi şablonu

[Django](https://www.djangoproject.com/) hızlı, güvenli ve ölçeklenebilir bir web geliştirme için tasarlanmış bir çerçevedir üst düzey Python. Visual Studio'da Python desteği Django tabanlı web uygulamasının yapısını oluşturma birkaç proje şablonları sağlar. Visual Studio'da bir şablon kullanmak için **dosya** > **yeni** > **proje**aramak için "Django" ve "boş Django Web sunucusundan seçin Proje,""Django Web projesi"ve"Yoklamalar Django Web projesi"şablonları. Bkz: [öğrenme Django öğretici](learn-django-in-visual-studio-step-01-project-and-solution.md) tüm şablonları kılavuz.

Visual Studio, Django projeleri için IntelliSense sağlar:

- Bağlam değişkenleri şablonuna geçirildi:

    ![Bağlam değişkenleri için IntelliSense](media/template-django-intellisense.png)

- Etiketleme ve her iki öğelerin filtreleme ve kullanıcı tanımlı:

    ![Etiketleri ve filtreleri için IntelliSense](media/template-django-intellisense-filter.png)

- Katıştırılmış CSS ve JavaScript için renklendirme sözdizimi:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio ayrıca sağlar tam [hata ayıklama desteği](debugging-python-in-visual-studio.md) Django projeleri için: 

![Kesme noktaları](media/template-django-debugging.png)

Üzerinden yönetilecek Django projeleri için tipik kendi `manage.py` Visual Studio izleyen varsayılır dosya. Bu dosya giriş noktası olarak kullanarak durdurursanız, aslında proje dosyası bölün. Bu durumda, gerek [var olan dosyaları projeden yeniden](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) Django projesi olarak işaretleme olmadan.

## <a name="django-management-console"></a>Django Yönetim Konsolu

Django Yönetim Konsolu aracılığıyla çeşitli komutlar üzerinde erişilen **proje** menüsü veya Çözüm Gezgini'nde projeye sağ tıklanarak.

- **Django Kabuğu'nu açın...** : uygulama içeriğiniz Modellerinizi yönetmenize olanak sağlayan bir Kabuğu'nu açar "

    ![Konsol](media/template-django-console-shell.png)

- **Django eşitleme DB**: yürütür `manage.py syncdb` etkileşimli bir pencere olarak:

    ![Konsol](media/template-django-console-sync-db.png)

- **Statik toplamak**: yürütür `manage.py collectstatic --noinput` tarafından belirtilen yol için tüm statik dosyaları kopyalamak için `STATIC_ROOT` içinde `settings.py`. Zaman [Azure App Service'te yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md), statik dosyalar, yayımlama işleminin bir parçası olarak otomatik olarak toplanır.

    ![Konsol](media/template-django-console-collect-static.png)

- **Doğrulama**: yürütür `manage.py validate`, tüm doğrulama hatalarını tarafından belirtilen yüklü modellerde raporları `INSTALLED_APPS` içinde `settings.py`:

    ![Konsol](media/template-django-console-validate.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Learning Django Öğreticisi](learn-django-in-visual-studio-step-01-project-and-solution.md)
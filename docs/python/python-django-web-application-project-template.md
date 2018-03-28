---
title: Django web projesi şablonu Python için | Microsoft Docs
description: Visual Studio şablonları Django framework kullanarak Python içinde yazılmış web uygulamaları için genel bakış.
ms.custom: ''
ms.date: 07/13/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 941ec5191e440be95d66da983508de36cef6d4fd
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
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

Visual Studio ayrıca sağlar tam [hata ayıklama desteği](debugging-python-in-visual-studio.md) Django projeleri için: 

![Kesme noktaları](media/template-django-debugging.png)

Üzerinden yönetilecek Django projeleri için tipik kendi `manage.py` Visual Studio izleyen varsayılır dosya. Bu dosya giriş noktası olarak kullanarak durdurursanız, aslında proje dosyası bölün. Bu durumda, gerek [var olan dosyaları projeden yeniden](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) Django projesi olarak işaretleme olmadan.

## <a name="django-management-console"></a>Django Yönetim Konsolu

Django Yönetim Konsolu aracılığıyla çeşitli komutlar üzerinde erişilen **proje** menüsü veya Çözüm Gezgini'nde projeye sağ tıklanarak.

- **Django Kabuğu'nu açın...** : uygulama içeriğiniz Modellerinizi yönetmenize olanak sağlayan bir Kabuğu'nu açar "

    ![Konsol](media/template-django-console-shell.png)

- **Django eşitleme DB**: yürütür `manage.py syncdb` etkileşimli bir pencere olarak:

    ![Konsol](media/template-django-console-sync-db.png)

- **Statik toplamak**: yürütür `manage.py collectstatic --noinput` tarafından belirtilen yol için tüm statik dosyaları kopyalamak için `STATIC_ROOT` içinde `settings.py`. Unutmayın [Microsoft Azure yayımlama](python-web-application-project-templates.md#publishing-to-azure-app-service), statik dosyalar, yayımlama işleminin bir parçası olarak otomatik olarak toplanır.

    ![Konsol](media/template-django-console-collect-static.png)

- **Doğrulama**: yürütür `manage.py validate`, tüm doğrulama hatalarını tarafından belirtilen yüklü modellerde raporları `INSTALLED_APPS` içinde `settings.py`:

    ![Konsol](media/template-django-console-validate.png)
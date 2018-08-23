---
title: VSPackage'ı durumu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- state, VSPackages
- VSPackages, managing application state
- state persistence
ms.assetid: 6056a9ea-e7a8-481c-9fc8-340229fa12d9
caps.latest.revision: 25
manager: douge
ms.openlocfilehash: 2891e3f8f9022aad3d16245ae1553a1a9fec3ec7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690489"
---
# <a name="vspackage-state"></a>VSPackage'ı durumu
Pek çok etken kalıcı değerleri ya da durumu, belirlemek bir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] uygulama.  
  
-   Projeler, proje ve yapılandırma özelliklerine sahiptir.  
  
-   Çözüm özellikleri vardır.  
  
-   Kullanıcı ayarları, belge pencerelerini, araç pencerelerini, yerleştirme durumu ve klavye kısayolları konumunu ve boyutunu belirler.  
  
-   Uygulamalar kullanıcı seçenekleri sahip olabilir.  
  
-   Uygulamanın oluşturduğu nesneler, kendi özelliklerine sahip olabilir.  
  
 Bazı yollar şunlardır, bir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] uygulama durumu yönetilebilir:  
  
-   Proje ve çözüm özellik sayfaları.  
  
-   Aracılığıyla **içeri ve dışarı aktarma ayarları Sihirbazı**, ayarları bir bilgisayardan diğerine taşımak bir kullanıcı etkinleştirir.  
  
-   Aracılığıyla **seçenekleri** iletişim kutusunda, uygulamalarla ilgili seçenekleri içerir.  
  
-   Aracılığıyla **özellikleri** nesnelerin özelliklerini sunan penceresi.  
  
-   Otomasyon sayesinde. Bir uygulama için Otomasyon karşılaştıklarını VSPackage ve nesne özelliklerine erişebilirsiniz.  
  
 Uygulama durumunu temel uygulama durumunu geri ve kaydedilmesini sağlayan çeşitli Kalıcılık mekanizmasıdır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Durum Kalıcılık desteği](../misc/support-for-state-persistence.md)  
 VSPackage durumu sıfırlanıyor kaydetme ve geri yükleme için yaygın stratejileri listelenmektedir.  
  
 [Seçenekler ve Seçenekler Sayfaları](../extensibility/internals/options-and-options-pages.md)  
 Genel ve özel seçenekler sayfaları tanıtır ve bunların nasıl uygulanacağını açıklar.  
  
 [Seçenekler Sayfası Oluşturma](../extensibility/creating-an-options-page.md)  
 İki seçenekler sayfaları, basit bir sayfa ve bir özel sayfa nasıl oluşturulacağını açıklar.  
  
 [Ayarlar kategorileri için destek](../misc/support-for-settings-categories.md)  
 Kullanıcı ayarlarını ve nasıl bunlar oluşturulan ve kalıcı açıklanır.  
  
 [Ayarları Kategorisi Oluşturma](../extensibility/creating-a-settings-category.md)  
 Nasıl oluşturulacağını açıklayan bir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ayarları kategorisi ve değerleri kaydedin ve ayarları dosyasından değerleri geri yüklemek için kullanabilirsiniz.  
  
 [Özellikleri ve Özellik Penceresini Genişletme](../extensibility/extending-properties-and-the-property-window.md)  
 Görüntülemek ve bir nesnenin değerini değiştirmek açıklanmaktadır **özellikleri** penceresi.  
  
 [Özellikleri ve Özellik Penceresini Kullanıma Sunma](../extensibility/exposing-properties-to-the-properties-window.md)  
 Bir nesnenin ortak özellikler kullanıma açıklanmaktadır **özellikleri** penceresi.  
  
 [Proje ve Yapılandırma Özellikleri için Destek](../extensibility/internals/support-for-project-and-configuration-properties.md)  
 Görüntüleme ve yapılandırma özelliklerini değiştirme açıklanmaktadır.  
  
 [Proje Özelliklerini Alma](../extensibility/getting-project-properties.md)  
 Proje Özellikleri görüntüleyen bir araç penceresinde yönetilen VSPackage'ı oluşturma adımlarında yol gösterir.  
  
 [Ayarlar Deposu Kullanma](../extensibility/using-the-settings-store.md)  
 Ayarları Store Kalıcılık mekanizması ve nasıl kullanılacağını açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VSPackage’lar](../extensibility/internals/vspackages.md)  
 Bir genel yönlendirme oluşturma ve VSPackages kullanma açıklayan konulara sağlar.
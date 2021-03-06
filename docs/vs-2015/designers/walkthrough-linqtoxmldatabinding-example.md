---
title: 'İzlenecek yol: LinqToXmlDataBinding örneği | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 723f6b121d844fa5a8e504e8106fdcfc6c58f012
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691793"
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>İzlenecek yol: LinqToXmlDataBinding örneği
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [izlenecek yol: LinqToXmlDataBinding örneği](https://docs.microsoft.com/visualstudio/designers/walkthrough-linqtoxmldatabinding-example).  
  
Bu izlenecek yolda LinqToXmlDataBinding örneği ve daha ilgi çekici, iki birincil kaynak dosyaların içeriğini, L2DBForm.xaml ve L2DBForm.xaml.cs bazıları açıklanmaktadır.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu okumadan önce derleme ve açıklandığı gibi LinqToXmlDataBinding programı çalıştırın öneririz [nasıl yapılır: oluşturma ve çalıştırma LinqToXmlDataBinding örneği](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşan bir Windows Presentation Foundation (WPF) uygulaması C# ve XAML kaynak dosyaları LinqToXmlDataBinding programdır. Kitap listesi tanımlar ve görüntüleme, ekleme, silme ve bu girişleri düzenlemek kullanıcının sağlayan gömülü bir XML belgesi içeriyor. Bunu, aşağıdaki iki birincil kaynak dosyalardan oluşur:  
  
-   L2DBForm.XAML ana penceresinin kullanıcı arabirimi (UI) XAML bildirimi kodunu içerir. Ayrıca, bir veri sağlayıcısı ve kitap listeleri için katıştırılmış XML belgesi tanımlayan bir pencere kaynak bölümü içerir.  
  
-   L2DBForm.xaml.cs başlatma ve kullanıcı Arabirimi ile ilişkili olay işleme yöntemleri içerir.  
  
 Ana pencereyi aşağıdaki dört dikey UI bölümlere ayrılmıştır:  
  
-   **XML** ham XML kaynağını katıştırılmış kitap listesi görüntüler.  
  
-   **Kitap listesi** defteri girdileri standart metin olarak görüntüler ve seçin ve tek tek girişleri silmek sağlar.  
  
-   **Seçili kitap Düzenle** seçili rehberi girişiyle ilişkili değerlerini düzenlemek kullanıcının sağlar.  
  
-   **Yeni kitabı ekleme** kullanıcı tarafından girilen değerleri temel alarak yeni bir kitap giriş oluşturulmasını sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[L2DBForm.xaml Kaynak Kodu](../designers/l2dbform-xaml-source-code.md)|İçeriği ve XAML kodu dosyasında L2DBForm.xaml açıklamasını içerir.|  
|[L2DBForm.xaml.cs Kaynak Kodu](../designers/l2dbform-xaml-cs-source-code.md)|İçeriği ve C# kaynak kodu dosyasında L2DBForm.xaml.cs açıklamasını içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to XML örneği kullanarak WPF verilerini bağlama](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [Nasıl Yapılır: LinqToXmlDataBinding Oluşturma ve Çalıştırma Örneği](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)




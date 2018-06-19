---
title: 'İzlenecek yol: LinqToXmlDataBinding örneği'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aa99324969f7fedfea7596dce55f9167ad6bb9a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917169"
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>İzlenecek yol: LinqToXmlDataBinding örneği
Bu kılavuzda LinqToXmlDataBinding örnek ve iki birincil kaynak dosyaları, L2DBForm.xaml ve L2DBForm.xaml.cs daha ilginç içeriği bazıları açıklanmaktadır.

## <a name="prerequisites"></a>Önkoşullar
 Bu kılavuzu okumadan önce yüksek oranda derleme ve açıklandığı gibi LinqToXmlDataBinding programı çalıştırma önerilir [nasıl yapılır: derleme ve çalıştırma LinqToXmlDataBinding örnek](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md).

## <a name="remarks"></a>Açıklamalar
 LinqToXmlDataBinding programın oluşan bir Windows Presentation Foundation (WPF) C# ve XAML kaynak dosyaları uygulamasıdır. Books listesini tanımlar ve görüntülemek, ekleme, silme ve bu girişleri düzenlemek kullanıcının sağlayan katıştırılmış bir XML belgesi içeriyor. Aşağıdaki iki birincil kaynak dosyalarını oluşur:

-   L2DBForm.XAML ana penceresinin kullanıcı arabirimi (UI) XAML bildirim kodunu içerir. Ayrıca, bir veri sağlayıcısı ve katıştırılmış XML belgesi kitap listelerin tanımlayan bir pencere kaynak bölümü içerir.

-   L2DBForm.xaml.cs başlatma ve kullanıcı Arabirimi ile ilişkili olay işleme yöntemleri içerir.

 Ana penceresinde, aşağıdaki dört dikey UI bölümlere ayrılmıştır:

-   **XML** katıştırılmış kitap listenin ham XML kaynağını görüntüler.

-   **Kitap listesi** defteri girdileri standart metin olarak görüntüler ve kullanıcının seçin ve tek tek girişleri silmek sağlar.

-   **Seçili kitabı Düzenle** şu anda seçili defteri girişiyle ilişkili değerlerini düzenlemek kullanıcının sağlar.

-   **Yeni rehberi Ekle** kullanıcı tarafından girilen değerleri temel alarak yeni bir defteri girişi oluşturulmasını sağlar.

## <a name="in-this-section"></a>Bu Bölümde

|Konu|Açıklama|
|-----------|-----------------|
|[L2DBForm.xaml Kaynak Kodu](../designers/l2dbform-xaml-source-code.md)|İçeriği ve dosya L2DBForm.xaml XAML kodda açıklamasını içerir.|
|[L2DBForm.xaml.cs Kaynak Kodu](../designers/l2dbform-xaml-cs-source-code.md)|İçeriği ve C# kaynak kodu dosyasına L2DBForm.xaml.cs açıklamasını içerir.|

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML Kullanarak WPF Verilerini Bağlama Örneği](../designers/wpf-data-binding-using-linq-to-xml-example.md)
- [Nasıl Yapılır: LinqToXmlDataBinding Oluşturma ve Çalıştırma Örneği](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)
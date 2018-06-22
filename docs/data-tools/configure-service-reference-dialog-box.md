---
title: Hizmet Başvurusu Yapılandırma İletişim Kutusu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 93d39aedc04cbdaebc35c892a8393ca394f44898
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281072"
---
# <a name="configure-service-reference-dialog-box"></a>Hizmet Başvurusu Yapılandırma İletişim Kutusu

**Hizmet başvurusu Yapılandır** iletişim kutusu, Windows Communication Foundation (WCF) hizmetlerini davranışını yapılandırmanızı sağlar.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

Erişim için **hizmet başvurusu Yapılandır** iletişim kutusunda sağ tıklatıp hizmeti başvuru **Çözüm Gezgini** ve **hizmet başvurusu Yapılandır**. İletişim kutusunu tıklatarak da erişebilirsiniz **Gelişmiş** düğmesini **hizmet Başvurusu Ekle iletişim kutusu**.

## <a name="task-list"></a>Görev listesi

- Bir WCF Hizmeti barındırıldığı adresini değiştirmek için yeni adresini girin **adresi** alan.

- Bir WCF istemcisi sınıfları için erişim düzeyini değiştirmek için bir erişim düzeyi anahtar sözcük seçin **erişim düzeyi oluşturulan sınıflar için** listesi.

- Bir WCF Hizmeti yöntemleri zaman uyumsuz olarak çağırmak için seçin **zaman uyumsuz işlemler oluşturmak** onay kutusu.

- Bir WCF istemcisi ileti sözleşme türleri oluşturmak için seçin **her zaman ileti sözleşmeleri oluşturmak** onay kutusu.

- Liste veya sözlük koleksiyon türleri için bir WCF istemcisi belirtmek için türlerinden birini **koleksiyon türü** ve **sözlük koleksiyon türü** listeler.

- Tür paylaşımı devre dışı bırakmak için temizleyin **yeniden başvurulan derlemelerin türlerinde** onay kutusu. Başvurulan derlemeler bir kısmı için paylaşımı türünü etkinleştirmek için seçin **yeniden başvurulan derlemelerin türlerinde** onay kutusunu seçin **yeniden belirtilen başvurulan derlemelerin türlerinde**ve istediğiniz değerleri seçin başvurur **başvurulan derlemeler listesi**.

## <a name="uielement-list"></a>UIElement listesi

 **Adres**

 Burada bir hizmet başvurusu için bir hizmet arar Web adresini güncelleştirir. Örneğin, geliştirme sırasında hizmet bir geliştirme sunucusu üzerinde barındırılan ve daha sonra bir üretim sunucusu için bir adres değişikliği araya taşındı.

> [!NOTE]
> Address öğesi ne zaman kullanılabilir değil **hizmet başvurusu Yapılandır** iletişim kutusunda görüntülenen **hizmet Başvurusu Ekle iletişim kutusu**.

 **Oluşturulan sınıflar için erişim düzeyi**

 WCF istemci sınıfları için kod erişim düzeyini belirler.

> [!NOTE]
> Web sitesi projeleri için bu seçenek her zaman ayarlanır `Public` ve değiştirilemez. Daha fazla bilgi için bkz: [hizmet başvurularında sorun giderme](../data-tools/troubleshooting-service-references.md).

 **Zaman uyumsuz işlemler**

 WCF hizmet yöntemleri çağrılmadan olup olmadığını zaman uyumlu olarak belirler (varsayılan) veya zaman uyumsuz olarak.

 **Görev tabanlı işlemler**

 Zaman uyumsuz kodu yazarken bu seçenek, görev paralel kitaplığı (tanıtılan TPL) .NET 4 ile yararlanmak sağlar. Bkz: [görev paralel kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl).

 **İleti sözleşmeleri her zaman oluştur**

 İleti sözleşmesi türleri için bir WCF istemcisi oluşturulan olup olmadığını belirler. İleti sözleşmeleri hakkında daha fazla bilgi için bkz: [ileti sözleşmeleri kullanılıyor](/dotnet/framework/wcf/feature-details/using-message-contracts).

 **Koleksiyon türü**

 Liste koleksiyonu türü WCF istemcisi için belirtir. Varsayılan türdür <xref:System.Array>.

 **Sözlük koleksiyon türü**

 Sözlük koleksiyon türü için bir WCF istemcisi belirtir. Varsayılan türdür <xref:System.Collections.Generic.Dictionary%602>.

 **Başvurulan derlemeler içindeki türleri yeniden kullan**

 Bir WCF istemcisi ne hizmet eklenen veya güncelleştirilen yeni türleri oluşturma yerine başvurulan derlemelerin zaten yeniden dener olup olmadığını belirler. Varsayılan olarak, bu seçenek denetlenir.

 **Başvurulan tüm derlemelerde türleri yeniden kullan**

 Seçili olduğunda, içindeki tüm türler **başvurulan derlemeler listesi** mümkünse yeniden kullanılır. Varsayılan olarak, bu seçenek seçilidir.

 **Belirtilen başvurulan derlemelerin türleri yeniden kullan**

 Seçili olduğunda, yalnızca seçili türlerinde **başvurulan derlemeler listesi** yeniden kullanılır.

 **Başvurulan derlemeler listesi**

 Başvurulan derlemeler için proje veya Web sitesi listesini içerir. Seçtiğinizde, **yeniden belirtilen başvurulan derlemelerin türlerinde**, seçin veya ayrı ayrı derlemeler temizleyin.

 **Web Başvurusu Ekle**

 Görüntüler **Web Başvuru Ekle** iletişim kutusu.

> [!NOTE]
> Bu seçenek yalnızca 2.0 sürümünü hedefleyen projeler için kullanılması gereken [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

> [!NOTE]
> **Web Başvuru Ekle** düğmesi kullanılabilir yalnızca ne zaman **hizmet başvurusu Yapılandır** iletişim kutusunda görüntülenen **hizmet Başvurusu Ekle iletişim kutusu**.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: web hizmetine başvuru ekleme](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Windows Communication Foundation Hizmetleri ve WCF Veri Hizmetleri](../data-tools/configure-service-reference-dialog-box.md)
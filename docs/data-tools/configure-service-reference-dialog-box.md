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
ms.openlocfilehash: abdb65b32f5f660257ecdc4d94fd9fcc387686f5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="configure-service-reference-dialog-box"></a>Hizmet Başvurusu Yapılandırma İletişim Kutusu

**Hizmet başvurusu Yapılandır** iletişim kutusu, Windows Communication Foundation (WCF) hizmetlerini davranışını yapılandırmanızı sağlar.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

Erişim için **hizmet başvurusu Yapılandır** iletişim kutusunda sağ tıklatıp hizmeti başvuru **Çözüm Gezgini** ve **hizmet başvurusu Yapılandır**. İletişim kutusunu tıklatarak da erişebilirsiniz **Gelişmiş** düğmesini **hizmet Başvurusu Ekle iletişim kutusu**.

## <a name="task-list"></a>Görev Listesi

- Bir WCF Hizmeti barındırıldığı adresini değiştirmek için yeni adresini girin **adresi** alan.

- Bir WCF istemcisi sınıfları için erişim düzeyini değiştirmek için bir erişim düzeyi anahtar sözcük seçin **erişim düzeyi oluşturulan sınıflar için** listesi.

- Bir WCF Hizmeti yöntemleri zaman uyumsuz olarak çağırmak için seçin **zaman uyumsuz işlemler oluşturmak** onay kutusu.

- Bir WCF istemcisi ileti sözleşme türleri oluşturmak için seçin **her zaman ileti sözleşmeleri oluşturmak** onay kutusu.

- Liste veya sözlük koleksiyon türleri için bir WCF istemcisi belirtmek için türlerinden birini **koleksiyon türü** ve **sözlük koleksiyon türü** listeler.

- Tür paylaşımı devre dışı bırakmak için temizleyin **yeniden başvurulan derlemelerin türlerinde** onay kutusu. Başvurulan derlemeler bir kısmı için paylaşımı türünü etkinleştirmek için seçin **yeniden başvurulan derlemelerin türlerinde** onay kutusunu seçin **yeniden belirtilen başvurulan derlemelerin türlerinde**ve istediğiniz değerleri seçin başvurur **başvurulan derlemeler listesi**.

## <a name="uielement-list"></a>UIElement Listesi

 **Adres**

 Web adresini güncelleştirmek için burada bir hizmet başvurusu için bir hizmet arar kullanılır. Örneğin, geliştirme sırasında hizmet bir geliştirme sunucusu üzerinde barındırılan ardından daha sonra bir üretim sunucusu için bir adres değişikliği araya taşındı.

> [!NOTE]
> Address öğesi ne zaman kullanılabilir değil **hizmet başvurusu Yapılandır** iletişim kutusunda görüntülenen **hizmet Başvurusu Ekle iletişim kutusu**.

 **Oluşturulan sınıflar için erişim düzeyi**

 WCF istemci sınıfları için kod erişim düzeyini belirler.

> [!NOTE]
> Web sitesi projeleri için bu seçenek her zaman ayarlanır `Public` ve değiştirilemez. Daha fazla bilgi için bkz: [sorun giderme hizmeti başvuruları](../data-tools/troubleshooting-service-references.md).

 **Zaman uyumsuz işlemler**

 WCF hizmet yöntemleri zaman uyumlu olarak adlı olup olmadığını belirler (varsayılan) veya zaman uyumsuz olarak.

 **Görev tabanlı işlemler**

 Zaman uyumsuz kod yazarken, bu seçenek, görev paralel kitaplığı (tanıtılan TPL) .net 4 ile yararlanmak sağlar. Bkz: [görev paralel kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl).

 **İleti sözleşmeleri her zaman oluştur**

 İleti sözleşmesi türleri için bir WCF istemcisi oluşturulan olup olmadığını belirler. İleti sözleşmeleri hakkında daha fazla bilgi için bkz: [kullanarak ileti sözleşmeleri](/dotnet/framework/wcf/feature-details/using-message-contracts).

 **Koleksiyon türü**

 Liste koleksiyonu türü WCF istemcisi için belirtir. Varsayılan türdür <xref:System.Array>.

 **Sözlük koleksiyon türü**

 Sözlük koleksiyon türü için bir WCF istemcisi belirtir. Varsayılan türdür <xref:System.Collections.Generic.Dictionary%602>.

 **Başvurulan derlemeler içindeki türleri yeniden kullan**

 Bir WCF istemcisi yeniden kullanmak bir hizmet eklenen veya güncelleştirilen yeni türleri oluşturma yerine başvurulan derlemelerin zaten var deneyip denemeyeceğini belirler. Varsayılan olarak, bu seçenek denetlenir.

 **Başvurulan tüm derlemelerde türleri yeniden kullan**

 Seçili olduğunda, içindeki tüm türler **başvurulan derlemeler listesi** mümkünse yeniden kullanılır. Varsayılan olarak, bu seçenek seçilidir.

 **Belirtilen başvurulan derlemelerin türleri yeniden kullan**

 Seçili olduğunda, yalnızca seçili türlerinde **başvurulan derlemeler listesi** yeniden kullanılır.

 **Başvurulan derlemeler listesi**

 Başvurulan derlemeler için proje veya Web sitesi listesini içerir. Zaman **yeniden belirtilen başvurulan derlemelerin türlerinde** seçildiğinde, ayrı ayrı derlemeler seçilir veya temizlenir.

 **Web Başvurusu Ekle**

 Web Başvurusu Ekle iletişim kutusu görüntüler.

> [!NOTE]
> Bu seçenek yalnızca 2.0 sürümünü hedefleyen projeler için kullanılması gereken [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

> [!NOTE]
> **Web Başvuru Ekle** düğmesi durumda yalnızca **hizmet başvurusu Yapılandır** iletişim kutusunda görüntülenen **hizmet Başvurusu Ekle iletişim kutusu**.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Web hizmetine başvuru ekleme](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Windows Communication Foundation Hizmetleri ve WCF Veri Hizmetleri](../data-tools/configure-service-reference-dialog-box.md)
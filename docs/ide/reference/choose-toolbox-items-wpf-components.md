---
title: "Araç kutusu öğelerini, WPF bileşenlerini seçin | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.chooseitems.wpfcomponents
helpviewer_keywords:
- WPF Components tab, Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box, WPF Components tab
ms.assetid: 6ce1d178-88c0-4295-8915-59fdeedabb11
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8aaa76694a60aad5c8bfcc2dd6d26feac03ab6e1
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="choose-toolbox-items-wpf-components"></a>Araç Kutusu Öğelerini, WPF Bileşenlerini Seçme
Bu sekme, **araç kutusu öğelerini Seç** iletişim kutusunda, yerel bilgisayarınızda Windows Presentation Foundation (WPF) denetimleri kullanılabilir listesini görüntüler. Bu listeyi görüntülemek için seçin **araç kutusu öğelerini Seç** gelen **Araçları** görüntülemek için menüsünden **araç kutusu öğelerini Seç** iletişim kutusunu ve ardından kendi **WPF Bileşenleri** sekmesi. Listelenen bileşenler sıralamak için sütun başlığını seçin.  

-   Bir bileşenin yanındaki onay kutusunu seçili olduğunda, bu bileşen için bir simge görüntülenir **araç**.  

    > [!TIP]
    >  Proje belge düzenlenmek üzere açık bir WPF denetimi örneği eklemek için sürükleyin kendi **araç** Tasarım görünümü yüzeyine simgesi. Varsayılan biçimlendirme ve kodun bileşenin değiştirmek hazır, projenizin eklenir. Daha fazla bilgi için bkz: [araç kutusunu kullanarak](../../ide/using-the-toolbox.md).  

-   Bir bileşenin yanındaki onay kutusunu temizlendiğinde, karşılık gelen simgeyi kaldırılır **araç.**  

    > [!NOTE]
    >  Bunlar için simgeleri görüntülenir olup olmadığına bakılmaksızın, bilgisayarınızda yüklü .NET Framework bileşenlerini kullanılabilir durumda kalmasını **araç**.  

Sütunlarda **WPF bileşenleri** sekmesi aşağıdaki bilgileri içerir:  

Ad  
WPF denetimleri için bilgisayarın kayıt defterinde girişi mevcut adlarını listeler.  

Ad Alanı  
Hiyerarşisini görüntüler [.NET Framework sınıf API](/dotnet/api/?view=netframework-4.7) bileşen yapısını tanımlayan ad alanı. Bilgisayarınızda yüklü her .NET Framework ad alanındaki kullanılabilir bileşenleri listelemek için bu sütun sıralama.  

Derleme adı  
Her bileşen için ad alanı içeren .NET Framework derleme adını görüntüler. Bilgisayarınızda yüklü her .NET Framework derlemesi içinde yer alan ad alanlarını listelemek için bu sütun sıralama.  

Dizin  
.NET Framework derlemesinin konumunu görüntüler. Genel Derleme Önbelleği tüm derlemeler için varsayılan konumdur. Genel Derleme Önbelleği hakkında daha fazla bilgi için bkz: [derlemeler ve genel derleme önbelleği ile çalışma](/dotnet/framework/app-domains/working-with-assemblies-and-the-gac).  

## <a name="uielement-list"></a>UIElement Listesi  
**Filtre**  
Metin kutusunda sağladığınız dizenin göre WPF denetimleri listesini filtreler. Tüm eşleşmeleri herhangi birinden dört sütun gösterilir.  

**Temizle**  
Filtre dizesi temizler.  

**Gözat**  
Açılır **açık** iletişim kutusu, WPF denetimleri içeren derlemeler gezinmenize olanak sağlar. Genel Derleme Önbelleği'nde bulunmayan derlemelerini yüklemek için bunu kullanın.  

**Dil**  
Seçili WPF denetimi içeren derlemenin yerelleştirilmiş dilini gösterir.  

## <a name="limitations"></a>Sınırlamalar  
Özel denetim ekleme veya <xref:System.Windows.Controls.UserControl> araç kutusuna aşağıdaki sınırlamalara sahiptir:  

-   Dışında geçerli proje tanımlanan yalnızca özel denetimler için çalışır.  

-   Doğru hata ayıklama yayın veya yayın hata ayıklama çözüm yapılandırmasını değiştirdiğinizde güncelleştirmez. Başvuru proje başvurusu değil, ancak diskteki derleme için bunun yerine olmasıdır. Hata ayıklama sürüme değiştirdiğinizde denetimi geçerli çözümün bir parçası ise, projenizin denetimi hata ayıklama sürümü başvuru devam eder.  

Ayrıca, özel denetim ve bu meta veriler için tasarım zamanı meta veri uygulanırsa belirtir <xref:Microsoft.Windows.Design.ToolboxBrowsableAttribute> ayarlanır `false`, Denetim Araç Kutusu'nda görünmez.  

Ad alanı ve denetlemek için derleme eşleyerek denetimlerinizi XAML görünümünde doğrudan başvuruda bulunabilir.  

## <a name="see-also"></a>Ayrıca bkz.  
[Araç kutusu](../../ide/reference/toolbox.md)  
[WPF ile çalışmaya başlama](../../designers/getting-started-with-wpf.md)

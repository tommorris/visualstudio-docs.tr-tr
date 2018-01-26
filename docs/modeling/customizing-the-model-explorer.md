---
title: "Model Gezgini özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.explorerbehavior
helpviewer_keywords: Domain-Specific Language Tools, Domain-Specific Language Explorer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7380d4bcade2e93b7e9ab7302201b67df629e041
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="customizing-the-model-explorer"></a>Model Gezginini Özelleştirme
İçin etki alanına özgü dil Tasarımcısı görünümünü ve davranışını explorer'ın aşağıdaki gibi değiştirebilirsiniz:  
  
-   Pencere Başlığı değiştirin.  
  
-   Sekme simgesi değiştirin.  
  
-   Düğümler için simgeler olarak değişir.  
  
-   Düğümleri gizleyin.  
  
## <a name="changing-the-window-title"></a>Pencere başlığını değiştirme  
 Oluşturulan Gezgini penceresi başlığı değiştirmek için seçin **Explorer davranışı** içinde **DSL Explorer**ve ardından **özellikleri** penceresindeki ayarlayın  **Başlık** istediğiniz başlığı özelliğine.  
  
## <a name="changing-the-tab-icon"></a>Sekme simgesi değiştirme  
 Tab simgesi explorer değiştirmek için bir .bmp dosyasında 16 x 16 piksel simgesini kullanın. Simge dosyası \DslPackage\Resources\ klasöre yerleştirin ve sonra dosya adını değiştirin **ModelExplorerToolWindowBitmaps.bmp**. Örneğin, değişebilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] setup.ico simgesi dosya .bmp biçimine ve ona yeniden adlandırma **DSLLanguageName\DslPackage\Resources\ModelExplorerToolWindowBitmaps.bmp**. İle birlikte yerleştirildiğinde oluşturulan Tasarımcısı, explorer sekmesinde bu simge görüntülemek **Çözüm Gezgini**.  
  
## <a name="setting-custom-icons-on-explorer-nodes"></a>Explorer düğümlerinde özel simgeler ayarlama  
 Explorer düğümü ayarlarını kullanarak, Explorer'da düğümleri özelleştirebilirsiniz. Aşağıdaki yordamda, bir simge bir düğüm eklemek gösterilmiştir.  
  
#### <a name="to-add-an-icon-to-an-explorer-node"></a>Simge bir explorer düğüm eklemek için  
  
1.  Oluşturma bir [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] Görev akışı çözüm şablonu kullanarak çözümü.  
  
2.  Bir 16 x 16 piksel simgesini içeren bir .bmp dosyası put **Dsl\Resources** çözüm klasöründe.  
  
3.  İçinde **DSL Explorer**, sağ **Explorer davranışı** ve ardından **yeni Explorer düğümü ayarları Ekle**.  
  
     Bir **ExplorerNodeSettings** düğümü altında görünmektedir **özel düğüm ayarları** düğümü.  
  
4.  Seçin **ExplorerNodeSettings**ve ardından **özellikleri** penceresindeki ayarlayın **sınıfı** için **aktör**.  
  
5.  Ayarlama **simge görüntülenecek** simge dosyasının yolu.  
  
6.  Tüm Şablonları dönüştürme ve yapı ve çözümü çalıştırın.  
  
7.  Oluşturulan tasarımcısında örnek diyagramı açın.  
  
     Explorer üç göstermelidir **aktör** simge olan düğümleri.  
  
> [!NOTE]
>  Oluşturulan Gezgini'nde görüntülenen herhangi bir öğe için bir düğüm simgesi ayarladıysanız, tüm Gezgini düğümleri simgesi görüntüler. Hiçbir simge ayarlarsanız düğümleri varsayılan simgesini görüntüler.  
  
## <a name="changing-the-name-displayed-on-an-explorer-node"></a>Bir Explorer düğümünde görüntülenen adını değiştirme  
 Model öğelerini adlarının Gezgini içinde nasıl görüntüleneceğini değiştirebilirsiniz. Aşağıdaki yordamda, adını görüntülemek gösterilmiştir **görev** tarafından başvurulan bir **açıklama** açıklama düğümünde.  
  
#### <a name="to-display-a-property"></a>Bir özelliği görüntülemek için  
  
1.  Önceki yordamda oluşturduğunuz çözümü açın.  
  
2.  Olduğundan emin olun **açıklama** özellik adıyla role çokluğu ayarlayarak yalnızca bir tek etki alanı sınıfına başvuruyor **konuları** 0.. 1. Özellik adı duruma gelir **konu**, ve ilişki adı duruma gelir **CommentReferencesSubject**.  
  
3.  İçinde **DSL Explorer**, sağ **Explorer davranışı** ve ardından **yeni Explorer düğümü ayarları Ekle**.  
  
     Bir **ExplorerNodeSettings** düğümü altında görünmektedir **özel düğüm ayarları** düğümü.  
  
4.  Seçin **ExplorerNodeSettings**ve ardından **özellikleri** penceresindeki ayarlayın **sınıfı** için **açıklama**.  
  
5.  Sağ **açıklama** düğümünü ve ardından **yeni özellik yolu Ekle**.  
  
     Adlı yeni bir düğüm görünür **özelliği görüntülenen**.  
  
6.  Seçin **özelliği görüntülenen**ve ardından **özellikleri** penceresinde Değer alanını tıklatın **yolu için özellik**. Seçin **açıklama**, ardından **CommentReferencesSubject**, ardından **FlowElement**. Ortaya çıkan yol benzemelidir **CommentReferencesSubject.Subject/! Konu**.  
  
7.  Değer alanına **özelliği**seçin **adı**.  
  
8.  Tüm Şablonları dönüştürme ve yapı ve çözümünüzü çalıştırın.  
  
9. Oluşturulan tasarımcısında örnek diyagramı açın.  
  
10. Çizim bir **açıklama bağlayıcı** Açıklama öğesi arasında ve **Task1** diyagramda öğesi.  
  
     Explorer düğümü açıklama olarak görüntülemelidir **Task1**.  
  
## <a name="hiding-nodes"></a>Gizleme düğümleri  
 Kendi yoluna ekleyerek, Explorer'da bir düğümü gizleyebilirsiniz **gizli düğümleri** düğümünün **DSL Explorer**. Aşağıdaki yordamda gizlemek gösterilmiştir **açıklama** düğümleri.  
  
#### <a name="to-hide-an-explorer-node"></a>Bir explorer düğümü gizlemek için  
  
1.  Önceki yordamda oluşturduğunuz çözümü açın.  
  
2.  İçinde **DSL Explorer**, sağ **Explorer davranışı** ve ardından **yeni etki alanı yolu Ekle**.  
  
     A **etki alanı yolu** düğümü altında görünmektedir **gizli düğümleri**.  
  
3.  Seçin **etki alanı yolu**ve ardından **özellikleri** penceresinde Değer alanını tıklatın **yol tanımı**. Seçin **FlowGraph**, ardından **FlowGraphHasComments**. Ortaya çıkan yol benzemelidir **FlowGraphHasComments.Comments**  
  
4.  Tüm Şablonları dönüştürme ve yapı ve çözümünüzü çalıştırın.  
  
5.  Oluşturulan tasarımcısında örnek diyagramı açın.  
  
     Explorer yalnızca göstermelidir bir **aktörler** düğümünü ve değil gösterilip gösterilmeyeceğini **açıklamaları** düğümü.  
  
## <a name="see-also"></a>Ayrıca bkz.

[Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
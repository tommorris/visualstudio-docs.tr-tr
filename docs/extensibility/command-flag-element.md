---
title: Komut bayrağı öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CommandFlag element (VSCT XML schema)
- VSCT XML schema elements, CommandFlag
ms.assetid: 5ef63399-d2db-4dc1-97ce-be1bd4ef4e39
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 036b9658957b76b62e3a9b44b59e07700f276a32
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="command-flag-element"></a>Komut bayrağı öğesi
Üst öğesi değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CommandFlag>DynamicVisibility</CommandFlag>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümde geçerli öğe değerleri açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|AllowParams|Kullanıcılar komut parametreleri girebilirsiniz gösterir **komutu** komutu kurallı adı yazdığınızda penceresi.<br /><br /> Geçerlilik süresi: `Button`|  
|AlwaysCreate|Menü grupları ya da düğmeleri sahip olsa bile oluşturulur.<br /><br /> Geçerlilik süresi: `Menu`|  
|CaseSensitive|Kullanıcı girişi büyük/küçük harfe duyarlıdır.<br /><br /> Geçerlilik süresi: `Combo`|  
|CommandWellOnly|Bu bayrak komutu en üst düzey menüsünde görünmez ve bir klavye kısayolu bağlama için ek Kabuk özelleştirme için kullanılabilir hale getirmek istiyorsanız geçerlidir. VSPackage yüklendikten sonra bu komutları açarak özelleştirebileceğiniz **seçenekleri** iletişim kutusunu ve ardından komut yerleşimi altında düzenleme **klavye ortamı** kategorisi. Bu bayrak kısayol menüleri, araç çubukları, menü denetleyicileri veya alt menüler yerleştirme etkilemez.<br /><br /> İçin geçerli: `Button`, `Combo`|  
|DefaultDisabled|Bunu uygulayan VSPackage yüklü değilse varsayılan olarak, komutu devre dışı bırakılır veya `QueryStatus` yöntemi çağrılmadı.<br /><br /> İçin geçerli: `Button`, `Combo`|  
|DefaultDocked|Varsayılan olarak yerleştirildi. Her zaman yerleşik olduğundan bu ayarı artık araç çubukları geçerlidir.|  
|DefaultInvisible|Varsayılan olarak, komut bunu uygulayan VSPackage yüklü değilse, görünmezdir veya `QueryStatus` yöntemi çağrılmadı.<br /><br /> Bu birleştirme öneririz `DynamicVisibility` bayrağı.<br /><br /> İçin geçerli: `Button`, `Combo`, `Menu`|  
|DontCache|Geliştirme ortamı önbelleğe almaz `QueryStatus` bu komutun sonuçlarını yöntemi.<br /><br /> Bir menüyü bu menü denetleyicinin menü öğelerinden metnin önbelleğe almaz bildirir. Menü dinamik öğeleri veya dinamik metin öğelerini içerdiğinde bu bayrağı kullanın.<br /><br /> İçin geçerli: `Button`, `Menu`|  
|DynamicItemStart|Dinamik bir listesi başlangıcını gösterir. Bu sırayla çağırarak listesini oluşturmak ortam sağlar `QueryStatus` OLECMDERR_E_UNSUPPORTED bayrağı dönene kadar liste öğeleri yöntemi. En son kullanılan (MRU) listeleri ve pencere listeleri gibi bu öğeler için iyi çalışır.<br /><br /> Geçerlilik süresi: `Button`|  
|DynamicVisibility|Komut görünürlüğünü aracılığıyla değiştirilebilir `QueryStatus` yöntemi veya bağlam dahil GUID aracılığıyla `VisibilityConstraints` bölümü.<br /><br /> Menüleri ve araç penceresi araç çubukları, aynı ana penceresinde görünen değil en üst düzey araç çubukları görünen komutlarını uygular. Üst düzey araç çubuğu öğeleri devre dışı ancak OLECMDF_INVISIBLE bayrağı gelen döndürüldüğünde, gizli olmayan `QueryStatus` yöntemi. Araç penceresi çubuklarında görünür araç komutları gizlenebilir.<br /><br /> Menüde, bu bayrak, tüm üyeleri gizli olduğunda, otomatik olarak gizleneceğini de gösterir. En üst düzey menü Bu davranış zaten yüklü olduğu için alt menüler Bu bayrak genellikle atanır.<br /><br /> Bu bayrak ile birleştirilmelidir `DefaultInvisible` bayrağı.<br /><br /> İçin geçerli: `Button`, `Combo`, `Menu`|  
|Süzme|Altında filtreleme anahtarları konusuna [açılan öğesi](../extensibility/combo-element.md).<br /><br /> Geçerlilik süresi: `Combo`|  
|FixMenuController|Bu komutu bir menü denetleyicisinde konumlandırılır komutu her zaman varsayılan varsa, diğer bir deyişle, menü denetleyicisi düğmesini kendisini seçildiğinde komutu seçilir. Menü denetleyicisi varsa `TextIsAnchorCommand` menü denetleyicisi ayrıca sahip komut metnini alır sonra bayrağı ayarlanmışsa, `FixMenuController` bayrağı.<br /><br /> Menü denetleyicisinde yalnızca bir komuta olmalıdır `FixMenuController` bayrağı. Birden fazla komut şekilde işaretlenir, son komut menüsünde varsayılan komut haline gelir.<br /><br /> Geçerlilik süresi: `Button`|  
|IconAndText|Bir simge ve metin menü ve araç çubuğu gösterir.<br /><br /> İçin geçerli: `Button`, `Combo`, `Menu`|  
|NoAutoComplete|Otomatik Tamamlama özelliği devre dışıdır.<br /><br /> Geçerlilik süresi: `Combo`|  
|NoButtonCustomize|Bu düğme özelleştirme kullanıcı izin vermez.<br /><br /> İçin geçerli: `Button`, `Combo`|  
|NoKeyCustomize|Klavye özelleştirme etkinleştirmeyin.<br /><br /> İçin geçerli: `Button`, `Combo`|  
|NoShowOnMenuController|Bu komutu bir menü denetleyicisinde konumlandırılır, komut aşağı açılan listede görünmez.<br /><br /> Geçerlilik süresi: `Button`|  
|NotInTBList|Kullanılabilir araç çubukları listede görünmez. Yalnızca araç menü türleri için geçerli değil.<br /><br /> Geçerlilik süresi: `Menu`|  
|NoToolbarClose|Kullanıcı araç kapatamazsınız. Yalnızca araç menü türleri için geçerli değil.<br /><br /> Geçerlilik süresi: `Menu`|  
|PICT|Yalnızca bir simge bir araç çubuğu, ancak yalnızca bir menü metni göster. Hiçbir simge belirtilmezse, araç çubuğunda tıklanabilir bir boş alana gösterir.<br /><br /> Geçerlilik süresi: `Button`|  
|PostExec|Komut engelleyici olmayan hale getirir. Tüm ön-işleme sorguları tamamlanana kadar geliştirme ortamı yürütme erteler.<br /><br /> Geçerlilik süresi: `Button`|  
|RouteToDocs|Komutu etkin belgeye yönlendirilir.<br /><br /> Geçerlilik süresi: `Button`|  
|StretchHorizontally|Bu bayrak ayarlandığında, genişlik kutu için en küçük genişliği haline gelir ve araç çubuğunda yer ise, birleşik giriş kutusu kullanılabilir alanı dolduracak şekilde uzatılır. Bu yalnızca araç yatay olarak yerleştirilir ve tek bir birleşik giriş kutusu araç çubuğunda (bayrağı tüm ilk açılan kutu dışında göz ardı edilir) bayrağını kullanabilirsiniz ortaya çıkar.<br /><br /> Geçerlilik süresi: `Combo`|  
|TextMenuUseButton|Kullanım `ButtonText` menüler için alan. Varsayılan alan `MenuText` belirtilmişse.<br /><br /> Geçerlilik süresi: `Button`|  
|TextChanges|Komut veya menü metni çalışma zamanında aracılığıyla genellikle değiştirilebilir `QueryStatus` yöntemi.<br /><br /> İçin geçerli: `Button`, `Menu`|  
|TextChangesButton|Geçerlilik süresi: `Button`|  
|TextIsAnchorCommand|Menü denetleyicisi için menü metnin varsayılan (bağlantı) komuttan alınır. Bir bağlantı komutu seçili veya kilitli son komutudur. Bu bayrak ayarlanmazsa menü denetleyicisi kendi kullanır `MenuText` alan. Ancak, menü denetleyicisi tıklatarak hala son seçilen komutu bu denetleyicisinden sağlar.<br /><br /> Bu bayrak birleştirmek öneririz `TextChanges` bayrağı.<br /><br /> Bu bayrak, MenuController veya MenuControllerLatched yalnızca türü menüler için geçerlidir.<br /><br /> Geçerlilik süresi: `Menu`|  
|TextMenuCtrlUseMenu|Kullanım `MenuText` menü denetleyicilerinde alan. Varsayılan alan `ButtonText`.<br /><br /> Geçerlilik süresi: `Button`|  
|TextMenuUseButton|Kullanım `ButtonText` menüler için alan. Varsayılan alan `MenuText` belirtilmişse.<br /><br /> Geçerlilik süresi: `Button`|  
|TextOnly|Simgesi belirtilmiş olsa bile bir araç veya menü ancak hiçbir simge yalnızca metin göster.<br /><br /> Geçerlilik süresi: `Button`|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Buttons Öğesi](../extensibility/buttons-element.md)|Bir grup için sağlar [Button öğesi](../extensibility/button-element.md) öğeleri.|  
|[Menus Öğesi](../extensibility/menus-element.md)|Bir VSPackage uygulayan tüm menüleri tanımlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
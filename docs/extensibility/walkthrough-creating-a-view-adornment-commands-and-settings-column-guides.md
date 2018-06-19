---
title: Bir görünüm Adornment, komutları ve ayarlar oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 4a2df0a3-42da-4f7b-996f-ee16a35ac922
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 57a7696eae0da92d88babf64c580a4767775dffd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148200"
---
# <a name="walkthrough-creating-a-view-adornment-commands-and-settings-column-guides"></a>İzlenecek yol: bir görünüm Adornment, komutları ve ayarları (sütun kılavuzları) oluşturma
Visual Studio metin/Kod düzenleyicisinde komutlar ve görünüm efektleri ile genişletebilirsiniz.  Bu konu popüler uzantısına sahip bir özellik, sütun kılavuzları başlayacağınızı gösterir.  Sütun kılavuzları kodunuzu belirli sütun genişliklerini yönetmenize yardımcı olmak için metin düzenleyici görünümünde çizilmiş görsel olarak açık satırlar gelir.  Özel olarak biçimlendirilmiş kod belgeleri, blog gönderileri, dahil etmek veya raporları hata örnekleri için önemli olabilir.  
  
 Bu kılavuzda, şunları yapacaksınız:  
  
-   VSIX proje oluşturma  
  
-   Bir düzenleyici görünüm adornment Ekle  
  
-   Kaydetme ve ayarları (çizim sütun kılavuzları ve bunların renk) olmanın desteği ekleme  
  
-   Komutları ekleyin (sütun kılavuzları Ekle/Kaldır, kendi rengi değiştirme)  
  
-   Düzen menüsü ve metin belgesi bağlam menülerini komutları koyun  
  
-   Visual Studio komut penceresinde komutlar çalıştırma desteği ekleme  
  
 Bu Visual Studio Galerisi sütun kılavuzları özelliğiyle sürümü deneyebilirsiniz[uzantısı](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
 **Not**: Bu kılavuzda, çok fazla kod visual studio uzantısı şablonları tarafından oluşturulan birkaç dosyaları yapıştırın, ancak bu kılavuzda diğer uzantısı örnekleriyle github'da tamamlanmış bir çözüme en kısa sürede başvurur.  Generictemplate simgeler kullanmak yerine gerçek komut simgeleri sahip tamamlanan kodu biraz farklıdır.  
  
## <a name="getting-started"></a>Başlarken  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="setting-up-the-solution"></a>Çözüm ayarlama  
 İlk VSIX proje oluşturma Düzenleyicisi görünüm adornment ekleyin ve sonra (komutu sahibi VSPackage ekler) bir komut ekleyin.  Temel mimari aşağıdaki gibidir:  
  
-   Oluşturan metin görünüm oluşturma dinleyici sahip bir `ColumnGuideAdornment` görünüm başına nesne.  Bu nesne görünümü değiştirme hakkında olayları dinleyen veya ayarları değiştirme, güncelleştirme ya da yeniden sütun gerektiği şekilde size yol gösterir.  
  
-   Var olan bir `GuidesSettingsManager` okuma ve yazma Visual Studio ayarları depolama biriminden işler.  Ayarlar Yöneticisi ayrıca kullanıcı komutları desteği ayarlarını güncelleştirme işlemleri sahiptir (sütun ekleyin, sütun kaldırma, renk değiştirme).  
  
-   Kullanıcı komut sahipse gereklidir VSIP paket yoktur ancak yalnızca komutları uygulama nesnesi başlatır Demirbaş kod.  
  
-   Var olan bir `ColumnGuideCommands` kullanıcı komutları uygulayan ve komutlar için komut işleyicileri kancalarını nesne .vsct dosyasında bildirildi.  
  
 **VSIX**.  Kullanım **dosya &#124; yeni...**  bir proje oluşturmak için komutu.  Sol Gezinti Bölmesi'nde genişletilebilirlik düğümünde C# ' ı seçin ve Seç **VSIX proje** sağ bölmede.  ColumnGuides adı girin ve seçin **Tamam** projesi oluşturmak için.  
  
 **Görüntüleme adornment**.  Çözüm Gezgini'nde proje düğümüne sağ işaretçi düğmesine basın.  Seçin **ekleme &#124; yeni öğe...**  yeni bir görünüm adornment öğesi eklemek için komutu.  Seçin **genişletilebilirlik &#124; Düzenleyicisi** sol gezinti bölmesinde ve **Düzenleyicisi görünüm penceresinin Adornment** sağ bölmede.  Öğe adı olarak ColumnGuideAdornment adını girin ve seçin **Ekle** ekleyin.  
  
 Proje (yanı sıra başvuruları ve benzeri) Bu öğe şablonu eklenen iki dosya görebilirsiniz: ColumnGuideAdornment.cs ve ColumnGuideAdornmentTextViewCreationListener.cs.  Şablonları yalnızca görünümünde mor dikdörtgen çizin.  Aşağıda birkaç görünüm oluşturma dinleyicisi satırları değiştirmek ve ColumnGuideAdornment.cs içeriğini değiştirin.  
  
 **Komutları**.  Çözüm Gezgini'nde proje düğümüne sağ işaretçi düğmesine basın.  Seçin **ekleme &#124; yeni öğe...**  yeni bir görünüm adornment öğesi eklemek için komutu.  Seçin **genişletilebilirlik &#124; VSPackage** sol gezinti bölmesinde ve **özel komut** sağ bölmede.  Öğe adı olarak ColumnGuideCommands adını girin ve seçin **Ekle** ekleyin.  Birkaç başvuruları ek olarak, komutlar ve paket ColumnGuideCommands.cs, ColumnGuideCommandsPackage.cs ve ColumnGuideCommandsPackage.vsct eklenmeden.  Aşağıda tanımlamak ve komutları uygulamak için ilk ve son dosyaların içeriğini yerini alır.  
  
## <a name="setting-up-the-text-view-creation-listener"></a>Metin görünümü oluşturma dinleyicisi ayarlama  
 ColumnGuideAdornmentTextViewCreationListener.cs düzenleyicisinde açın.  Visual Studio metin görünümler her oluşturur için bu kodu bir işleyici uygular.  İşleyici görünümü özelliklere bağlı olarak zaman çağrıldığını denetim özniteliği vardır.  
  
 Kod ayrıca bir adornment katmanı bildirmeniz gerekir.  Düzenleyici görünümleri güncelleştirdiğinde adornment katmanları görünümü alır ve değerinden adornment öğeleri alır.  Başkalarının göre katmanınız özniteliklerle sıralama bildirebilirsiniz.  Aşağıdaki satırı değiştirin:  
  
```csharp  
[Order(After = PredefinedAdornmentLayers.Caret)]  
```  
  
 Bu iki satır ile:  
  
```csharp  
[Order(Before = PredefinedAdornmentLayers.Text)]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
```  
  
 Değiştirdiğiniz satır adornment katman bildirme özniteliklerin grupta yer.   İlk satırı sütun kılavuz çizgileri göründüğü yalnızca değişiklikler değiştirildi.  "Önce" görünümündeki metni arkasında veya metni altında göründükleri anlamına gelir satırlar çizme.  İkinci satır, sütun kılavuzu adornments, bir belge kavramı uyan metin varlıklar için geçerli olmasına rağmen adornment Örneğin, yalnızca çalışma düzenlenebilir metin bildirebilirsiniz bildirir.  Daha fazla bilgi bulunmaktadır [dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)  
  
## <a name="implementing-the-settings-manager"></a>Uygulama ayarları Yöneticisi  
 GuidesSettingsManager.cs içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using Microsoft.VisualStudio.Settings;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Settings;  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows.Media;  
  
namespace ColumnGuides  
{  
    internal static class GuidesSettingsManager  
    {  
        // Because my code is always called from the UI thred, this succeeds.  
        internal static SettingsManager VsManagedSettingsManager =  
            new ShellSettingsManager(ServiceProvider.GlobalProvider);  
  
        private const int _maxGuides = 5;  
        private const string _collectionSettingsName = "Text Editor";  
        private const string _settingName = "Guides";  
        // 1000 seems reasonable since primary scenario is long lines of code  
        private const int _maxColumn = 1000;   
  
        static internal bool AddGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column",  
                    "The paramenter must be between 1 and " + _maxGuides.ToString());  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            if (offsets.Count() >= _maxGuides)  
                return false;  
            // Check for duplicates  
            if (offsets.Contains(column))  
                return false;  
            offsets.Add(column);  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, offsets);  
            return true;  
        }  
  
        static internal bool RemoveGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column", "The paramenter must be between 1 and 10,000");  
            var columns = GuidesSettingsManager.GetColumnOffsets();  
            if (! columns.Remove(column))  
            {  
                // Not present.  Allow user to remove the last column   
                // even if they're not on the right column.  
                if (columns.Count != 1)  
                    return false;  
  
                columns.Clear();  
            }  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, columns);  
            return true;  
        }  
  
        static internal bool CanAddGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                return false;  
            var offsets = GetColumnOffsets();  
            if (offsets.Count >= _maxGuides)  
                return false;  
            return ! offsets.Contains(column);  
        }  
  
        static internal bool CanRemoveGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                return false;  
            // Allow user to remove the last guideline regardless of the column.  
            // Okay to call count, we limit the number of guides.  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            return offsets.Contains(column) || offsets.Count() == 1;  
        }  
  
        static internal void RemoveAllGuidelines()  
        {  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, new int[0]);  
        }  
  
        private static bool IsValidColumn(int column)  
        {  
            // zero is allowed (per user request)  
            return 0 <= column && column <= _maxColumn;  
        }  
  
        // This has format "RGB(<int>, <int>, <int>) <int> <int>...".  
        // There can be any number of ints following the RGB part,   
        // and each int is a column (char offset into line) where to draw.  
        static private string _guidelinesConfiguration;  
        static private string GuidelinesConfiguration  
        {  
            get  
            {  
                if (_guidelinesConfiguration == null)  
                {  
                    _guidelinesConfiguration =   
                        GetUserSettingsString(  
                            GuidesSettingsManager._collectionSettingsName,  
                            GuidesSettingsManager._settingName)  
                        .Trim();  
                }  
                return _guidelinesConfiguration;  
            }  
  
            set  
            {  
                if (value != _guidelinesConfiguration)  
                {  
                    _guidelinesConfiguration = value;  
                    WriteUserSettingsString(  
                        GuidesSettingsManager._collectionSettingsName,  
                        GuidesSettingsManager._settingName, value);  
                    // Notify ColumnGuideAdornments to update adornments in views.  
                    var handler = GuidesSettingsManager.SettingsChanged;  
                    if (handler != null)  
                        handler();  
                }  
            }  
        }  
  
        internal static string GetUserSettingsString(string collection, string setting)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetReadOnlySettingsStore(SettingsScope.UserSettings);  
            return store.GetString(collection, setting, "RGB(255,0,0) 80");  
        }  
  
        internal static void WriteUserSettingsString(string key, string propertyName,  
                                                     string value)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetWritableSettingsStore(SettingsScope.UserSettings);  
            store.CreateCollection(key);  
            store.SetString(key, propertyName, value);  
        }  
  
        // Persists settings and sets property with side effect of signaling  
        // ColumnGuideAdornments to update.  
        static private void WriteSettings(Color color, IEnumerable<int> columns)  
        {  
            string value = ComposeSettingsString(color, columns);  
            GuidelinesConfiguration = value;  
        }  
  
        private static string ComposeSettingsString(Color color,  
                                                    IEnumerable<int> columns)  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendFormat("RGB({0},{1},{2})", color.R, color.G, color.B);  
            IEnumerator<int> columnsEnumerator = columns.GetEnumerator();  
            if (columnsEnumerator.MoveNext())  
            {  
                sb.AppendFormat(" {0}", columnsEnumerator.Current);  
                while (columnsEnumerator.MoveNext())  
                {  
                    sb.AppendFormat(", {0}", columnsEnumerator.Current);  
                }  
            }  
            return sb.ToString();  
        }  
  
        // Parse a color out of a string that begins like "RGB(255,0,0)"  
        static internal Color GuidelinesColor  
        {  
            get  
            {  
                string config = GuidelinesConfiguration;  
                if (!String.IsNullOrEmpty(config) && config.StartsWith("RGB("))  
                {  
                    int lastParen = config.IndexOf(')');  
                    if (lastParen > 4)  
                    {  
                        string[] rgbs = config.Substring(4, lastParen - 4).Split(',');  
  
                        if (rgbs.Length >= 3)  
                        {  
                            byte r, g, b;  
                            if (byte.TryParse(rgbs[0], out r) &&  
                                byte.TryParse(rgbs[1], out g) &&  
                                byte.TryParse(rgbs[2], out b))  
                            {  
                                return Color.FromRgb(r, g, b);  
                            }  
                        }  
                    }  
                }  
                return Colors.DarkRed;  
            }  
  
            set  
            {  
                WriteSettings(value, GetColumnOffsets());  
            }  
        }  
  
        // Parse a list of integer values out of a string that looks like  
        // "RGB(255,0,0) 1, 5, 10, 80"  
        static internal List<int> GetColumnOffsets()  
        {  
            var result = new List<int>();  
            string settings = GuidesSettingsManager.GuidelinesConfiguration;  
            if (String.IsNullOrEmpty(settings))  
                return new List<int>();  
  
            if (!settings.StartsWith("RGB("))  
                return new List<int>();  
  
            int lastParen = settings.IndexOf(')');  
            if (lastParen <= 4)  
                return new List<int>();  
  
            string[] columns = settings.Substring(lastParen + 1).Split(',');  
  
            int columnCount = 0;  
            foreach (string columnText in columns)  
            {  
                int column = -1;  
                // VS 2008 gallery extension didn't allow zero, so per user request ...  
                if (int.TryParse(columnText, out column) && column >= 0)  
                {  
                    columnCount++;  
                    result.Add(column);  
                    if (columnCount >= _maxGuides)  
                        break;  
                }  
            }  
            return result;  
        }  
  
        // Delegate and Event to fire when settings change so that ColumnGuideAdornments   
        // can update.  We need nothing special in this event since the settings manager   
        // is statically available.  
        //  
        internal delegate void SettingsChangedHandler();  
        static internal event SettingsChangedHandler SettingsChanged;  
  
    }  
}  
  
```  
  
 Bu kod çoğu yalnızca oluşturur ve ayarları biçimi ayrıştırır: "RGB (\<int >,\<int >,\<int >) \<int >, \<int >,...".  Sonunda tamsayılar sütun kılavuzları istediğiniz tabanlı sütunlar'dır.  Sütun kılavuzları uzantısı tek ayar değer dizesi tüm ayarlarını yakalar.  
  
 Vurgulama değerinde kodunun bazı bölümleri vardır.  Aşağıdaki kod satırını ayarları depolama için Visual Studio yönetilen sarmalayıcı alır.  Çoğunlukla, bu Windows kayıt defteri soyutlar, ancak bu API depolama mekanizmasını bağımsızdır.  
  
```csharp  
internal static SettingsManager VsManagedSettingsManager =  
    new ShellSettingsManager(ServiceProvider.GlobalProvider);  
```  
  
 Visual Studio ayarları depolama tüm ayarları benzersiz şekilde tanımlamak için bir kategori tanımlayıcısı ve ayar tanımlayıcısı kullanır:  
  
```csharp  
private const string _collectionSettingsName = "Text Editor";  
private const string _settingName = "Guides";  
```  
  
 Kullanmak zorunda değil `"Text Editor"` kategori olarak adı ve istediğiniz herhangi bir şey seçebilirsiniz.  
  
 İlk birkaç ayarlarını değiştirmek için giriş noktaları işlevlerdir.  Bunlar sayısı izin verilen kılavuzları gibi üst düzey kısıtlamaları denetleyin.  Bunlar çağrı sonra `WriteSettings` ayarları dizesi oluşturur ve özelliği ayarlar `GuideLinesConfiguration`.  Bu özelliği ayarlamak kaydeder ayarları değeri etkinleşir ve Visual Studio ayarları deposu `SettingsChanged` tüm güncelleştirmek için olay `ColumnGuideAdornment` nesneleri, her bir metin görünümü ile ilişkilendirilmiş.  
  
 Birkaç vardır giriş noktası işlevlerin gibi `CanAddGuideline`, ayarları değiştirmek komutları uygulamak için kullanılır.  Visual Studio menüleri gösterir, bu sorgular komutu şu anda, adını nedir etkin olup olmadığını görmek için komutu uygulamaları, vs.  Aşağıda bu giriş noktaları komutu uygulamaları için bağlanacağını nasıl görürsünüz.  Bkz: [genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md) komutları hakkında daha fazla bilgi için.  
  
## <a name="implementing-the-columnguideadornment-class"></a>ColumnGuideAdornment sınıfı  
 `ColumnGuideAdornment` Adornments olan her metin görünümünü sınıfının örneği.  Bu sınıf görünümü değiştirme hakkında olayları dinleyen veya ayarları değiştirme, güncelleştirme ya da yeniden sütun gerektiği şekilde size yol gösterir.  
  
 ColumnGuideAdornment.cs içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using System;  
using System.Windows.Media;  
using Microsoft.VisualStudio.Text.Editor;  
using System.Collections.Generic;  
using System.Windows.Shapes;  
using Microsoft.VisualStudio.Text.Formatting;  
using System.Windows;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Adornment class, one instance per text view that draws a guides on the viewport  
    /// </summary>  
    internal sealed class ColumnGuideAdornment  
    {  
        private const double _lineThickness = 1.0;  
        private IList<Line> _guidelines;  
        private IWpfTextView _view;  
        private double _baseIndentation;  
        private double _columnWidth;  
  
        /// <summary>  
        /// Creates editor column guidelines  
        /// </summary>  
        /// <param name="view">The <see cref="IWpfTextView"/> upon   
        /// which the adornment will be drawn</param>  
        public ColumnGuideAdornment(IWpfTextView view)  
        {  
            _view = view;  
            _guidelines = CreateGuidelines();  
            GuidesSettingsManager.SettingsChanged +=   
                new GuidesSettingsManager.SettingsChangedHandler(SettingsChanged);  
            view.LayoutChanged +=   
                new EventHandler<TextViewLayoutChangedEventArgs>(OnViewLayoutChanged);  
            _view.Closed += new EventHandler(OnViewClosed);  
        }  
  
        void SettingsChanged()  
        {  
            _guidelines = CreateGuidelines();  
            UpdatePositions();  
            AddGuidelinesToAdornmentLayer();  
        }  
  
        void OnViewClosed(object sender, EventArgs e)  
        {  
            _view.LayoutChanged -= OnViewLayoutChanged;  
            _view.Closed -= OnViewClosed;  
            GuidesSettingsManager.SettingsChanged -= SettingsChanged;  
        }  
  
        private bool _firstLayoutDone;  
  
        void OnViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
        {  
            bool fUpdatePositions = false;  
  
            IFormattedLineSource lineSource = _view.FormattedLineSource;  
            if (lineSource == null)  
            {  
                return;  
            }  
            if (_columnWidth != lineSource.ColumnWidth)  
            {  
                _columnWidth = lineSource.ColumnWidth;  
                fUpdatePositions = true;  
            }  
            if (_baseIndentation != lineSource.BaseIndentation)  
            {  
                _baseIndentation = lineSource.BaseIndentation;  
                fUpdatePositions = true;  
            }  
            if (fUpdatePositions ||  
                e.VerticalTranslation ||  
                e.NewViewState.ViewportTop != e.OldViewState.ViewportTop ||  
                e.NewViewState.ViewportBottom != e.OldViewState.ViewportBottom)  
            {  
                UpdatePositions();  
            }  
            if (!_firstLayoutDone)  
            {  
                AddGuidelinesToAdornmentLayer();  
                _firstLayoutDone = true;  
            }  
        }  
  
        private static IList<Line> CreateGuidelines()  
        {  
            Brush lineBrush = new SolidColorBrush(GuidesSettingsManager.GuidelinesColor);  
            DoubleCollection dashArray = new DoubleCollection(new double[] { 1.0, 3.0 });  
            IList<Line> result = new List<Line>();  
            foreach (int column in GuidesSettingsManager.GetColumnOffsets())  
            {  
                Line line = new Line()  
                {  
                    // Use the DataContext slot as a cookie to hold the column  
                    DataContext = column,  
                    Stroke = lineBrush,  
                    StrokeThickness = _lineThickness,  
                    StrokeDashArray = dashArray  
                };  
                result.Add(line);  
            }  
            return result;  
        }  
  
        void UpdatePositions()  
        {  
            foreach (Line line in _guidelines)  
            {  
                int column = (int)line.DataContext;  
                line.X2 = _baseIndentation + 0.5 + column * _columnWidth;  
                line.X1 = line.X2;  
                line.Y1 = _view.ViewportTop;  
                line.Y2 = _view.ViewportBottom;  
            }  
        }  
  
        void AddGuidelinesToAdornmentLayer()  
        {  
            // Grab a reference to the adornment layer that this adornment   
            // should be added to  
            // Must match exported name in ColumnGuideAdornmentTextViewCreationListener  
            IAdornmentLayer adornmentLayer =   
                _view.GetAdornmentLayer("ColumnGuideAdornment");  
            if (adornmentLayer == null)  
                return;  
            adornmentLayer.RemoveAllAdornments();  
            // Add the guidelines to the adornment layer and make them relative   
            // to the viewport  
            foreach (UIElement element in _guidelines)  
                adornmentLayer.AddAdornment(AdornmentPositioningBehavior.OwnerControlled,  
                                            null, null, element, null);  
        }  
    }  
  
}  
```  
  
 Bu sınıfın örnekleri, ilişkili tutun <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> ve listesini `Line` görünümünde çizilmiş nesneleri.  
  
 Oluşturucusu (çağrılır `ColumnGuideAdornmentTextViewCreationListener` Visual Studio yeni görünümler oluşturduğunda) sütun kılavuzu oluşturur `Line` nesneleri.  Oluşturucu için işleyiciler de ekler `SettingsChanged` olayı (tanımlanan `GuidesSettingsManager`) ve olaylarını görüntüle `LayoutChanged` ve `Closed`.  
  
 `LayoutChanged` Değişiklikleri görünümünde, Visual Studio görünümü oluşturduğunda dahil olmak üzere çeşitli türlerde nedeniyle olay etkinleşir.  `OnViewLayoutChanged` İşleyicisi çağrılarını `AddGuidelinesToAdornmentLayer` yürütülecek.  Kodda `OnViewLayoutChanged` yazı tipi boyutu değişiklikleri, görünüm boşluğu, yatay kaydırma ve benzerleri gibi değişikliklere göre satır konumlarını güncelleştirme gerekip gerekmediğini belirler.  Kodda `UpdatePositions` karakter veya metin satırının içinde belirtilen karakter uzaklığı bulunduğu metin sütunu hemen sonra çizmek kılavuz çizgileri neden olur.  
  
 Her ayarlarını değiştirme `SettingsChanged` işlevi yalnızca yeniden oluşturur tüm `Line` ne olursa olsun yeni ayarların ile nesneleri.  Kod satırı konumları ayarladıktan sonra önceki tüm kaldırır `Line` nesnelerin `ColumnGuideAdornment` adornment katman ve yenilerini ekler.  
  
## <a name="defining-the-commands-menus-and-menu-placements"></a>Komutlar, menüler ve menü yerleşimi tanımlama  
 Olabilir çok komutlar ve menüleri bildirme, diğer çeşitli menülerde komutlar veya menü grupları yerleştirme ve komut işleyicileri takma.  Bu kılavuzda bu uzantı, ancak daha ayrıntılı bilgi için komutları nasıl çalıştığını vurgular, bkz: [genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md).  
  
### <a name="introduction-to-the-code"></a>Giriş kodu  
 Sütun kılavuzları uzantısı gösteren bir öğeye ait komut grubunu bildirme (sütun ekleyin, sütunu kaldırın, çizgi rengini değiştirin) ve sonra o grubun düzenleyicisinin bağlam menüsünün alt menüde yerleştirerek.  Sütun kılavuzları uzantısını komutları ana da ekler. **Düzenle** menü ancak tutar bunları görünmez, genel bir desen aşağıda açıklanan.  
  
 Komutları uygulama için üç bölümden oluşur: ColumnGuideCommandsPackage.cs, ColumnGuideCommandsPackage.vsct ve ColumnGuideCommands.cs.  Şablonlar tarafından oluşturulan kodu bir komut yerleştirir **Araçları** uygulaması olarak bir iletişim kutusu açılır menü.  Oldukça basit olduğundan nasıl, .vsct ve ColumnGuideCommands.cs dosyalarında uygulanan bakabilirsiniz.  Bu dosyalar kodda yerini alır.  
  
 Paket uzantısını komutları ve komutları nereye sunar bulmak Visual Studio için gerekli olan Demirbaş bildirimleri kodudur.  Paket başlatır, bu örneği komutları uygulama sınıfı.  Komutları ilgili paketler hakkında daha fazla bilgi için yukarıda bağlantı komutları bakın.  
  
### <a name="a-common-commands-pattern"></a>Sık kullanılan komutlar düzeni  
 Sütun kılavuzları uzantısını komutları Visual Studio'da çok genel bir desen bir örnektir.  İlgili komutları bir gruba yerleştirmek ve o grubun ana menüsünde genellikle ile yerleştirdiğiniz "`<CommandFlag>CommandWellOnly</CommandFlag>`" komutu görünmez yapma ayarlayın.  Ana menülerde komutları koyma (gibi **Düzenle**) bu şekilde onlara iyi adları verir (gibi **Edit.AddColumnGuide**) anahtar bağlama yeniden atarken komutları bulmak için yararlı olan  **Araçlar Seçenekler** ve komutları çağrılırken, tamamlama almak **komut penceresi**.  
  
 Ardından bağlam menülerini komut grubunu ekleyin veya menü komutlarını kullanmak için kullanıcı beklediğiniz yerde sub.  Visual Studio değerlendirir `CommandWellOnly` bir görünmezlik bayrağı yalnızca ana menü olarak.  Bir bağlam menüsü veya alt menü komutları aynı kullanıcı grubunu yerleştirdiğinizde komutları görünür.  
  
 Yaygın olarak kullanılan deseni bir parçası olarak, sütun kılavuzları uzantısı tek alt menü tutan ikinci bir grup oluşturur.  Alt menü sırayla dört sütun kılavuzu komutlarla ilk grubu içerir.  Alt menü tutan ikinci bir alt menü bu bağlam menülerini getirecek çeşitli içerik menülerde yerleştirdiğiniz yeniden kullanılabilir varlık grubudur.  
  
### <a name="the-vsct-file"></a>.Vsct dosyası  
 .Vsct dosya komutları ve, simgeleri birlikte vb. gidebilecekleri bildirir.  .Vsct dosyasının içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <!--  This is the file that defines the actual layout and type of the commands.  
        It is divided in different sections (e.g. command definition, command  
        placement, ...), with each defining a specific set of properties.  
        See the comment before each section for more details about how to  
        use it. -->  
  
  <!--  The VSCT compiler (the tool that translates this file into the binary  
        format that VisualStudio will consume) has the ability to run a preprocessor  
        on the vsct file; this preprocessor is (usually) the C++ preprocessor, so  
        it is possible to define includes and macros with the same syntax used  
        in C++ files. Using this ability of the compiler here, we include some files  
        defining some of the constants that we will use inside the file. -->  
  
  <!--This is the file that defines the IDs for all the commands exposed by   
      VisualStudio. -->  
  <Extern href="stdidcmd.h"/>  
  
  <!--This header contains the command ids for the menus provided by the shell. -->  
  <Extern href="vsshlids.h"/>  
  
  <!--The Commands section is where commands, menus, and menu groups are defined.  
      This section uses a Guid to identify the package that provides the command   
      defined inside it. -->  
  <Commands package="guidColumnGuideCommandsPkg">  
    <!-- Inside this section we have different sub-sections: one for the menus, another    
    for the menu groups, one for the buttons (the actual commands), one for the combos   
    and the last one for the bitmaps used. Each element is identified by a command id  
    that is a unique pair of guid and numeric identifier; the guid part of the identifier  
    is usually called "command set" and is used to group different command inside a  
    logically related group; your package should define its own command set in order to  
    avoid collisions with command ids defined by other packages. -->  
  
    <!-- In this section you can define new menu groups. A menu group is a container for   
         other menus or buttons (commands); from a visual point of view you can see the   
         group as the part of a menu contained between two lines. The parent of a group   
         must be a menu. -->  
    <Groups>  
  
      <!-- The main group is parented to the edit menu. All the buttons within the group  
           have the "CommandWellOnly" flag, so they're actually invisible, but it means  
           they get canonical names that begin with "Edit". Using placements, the group  
           is also placed in the GuidesSubMenu group. -->  
      <!-- The priority 0xB801 is chosen so it goes just after   
           IDG_VS_EDIT_COMMANDWELL -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
      <!-- Group for holding the "Guidelines" sub-menu anchor (the item on the menu that  
           drops the sub menu). The group is parented to  
           the context menu for code windows. That takes care of most editors, but it's  
           also placed in a couple of other windows using Placements -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_CTXT_CODEWIN" />  
      </Group>  
  
    </Groups>  
  
    <Menus>  
      <Menu guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" priority="0x1000"  
            type="Menu">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup" />  
        <Strings>  
          <ButtonText>&Column Guides</ButtonText>  
        </Strings>  
      </Menu>  
    </Menus>  
  
    <!--Buttons section. -->  
    <!--This section defines the elements the user can interact with, like a menu command or a button   
        or combo box in a toolbar. -->  
    <Buttons>  
      <!--To define a menu group you have to specify its ID, the parent menu and its   
          display priority.   
          The command is visible and enabled by default. If you need to change the   
          visibility, status, etc, you can use the CommandFlag node.  
          You can add more than one CommandFlag node e.g.:  
              <CommandFlag>DefaultInvisible</CommandFlag>  
              <CommandFlag>DynamicVisibility</CommandFlag>  
          If you do not want an image next to your command, remove the Icon node or   
          set it to <Icon guid="guidOfficeIcon" id="msotcidNoIcon" /> -->  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
              priority="0x0100" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicAddGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Add Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveColumnGuide"   
              priority="0x0101" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicRemoveGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Remove Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidChooseGuideColor"   
              priority="0x0103" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicChooseColor" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Column Guide &Color...</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveAllColumnGuides"   
              priority="0x0102" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Remove A&ll Columns</ButtonText>  
        </Strings>  
      </Button>  
    </Buttons>  
  
    <!--The bitmaps section is used to define the bitmaps that are used for the  
        commands.-->  
    <Bitmaps>  
      <!--  The bitmap id is defined in a way that is a little bit different from the  
            others:   
            the declaration starts with a guid for the bitmap strip, then there is the  
            resource id of the bitmap strip containing the bitmaps and then there are   
            the numeric ids of the elements used inside a button definition. An important  
            aspect of this declaration is that the element id   
            must be the actual index (1-based) of the bitmap inside the bitmap strip. -->  
      <Bitmap guid="guidImages" href="Resources\ColumnGuideCommands.png"   
              usedList="bmpPicAddGuide, bmpPicRemoveGuide, bmpPicChooseColor" />  
    </Bitmaps>  
  
  </Commands>  
  
  <CommandPlacements>  
  
    <!-- Define secondary placements for our groups -->  
  
    <!-- Place the group containing the three commands in the sub-menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                      priority="0x0100">  
      <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
    </CommandPlacement>  
  
    <!-- The HTML editor context menu, for some reason, redefines its own groups  
         so we need to place a copy of our context menu there too. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_HTML" />  
    </CommandPlacement>  
  
    <!-- The HTML context menu in Dev12 changed. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp_Dev12" id="IDMX_HTM_SOURCE_HTML_Dev12" />  
    </CommandPlacement>  
  
    <!-- Similarly for Script -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_SCRIPT" />  
    </CommandPlacement>  
  
    <!-- Similarly for ASPX  -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_ASPX" />  
    </CommandPlacement>  
  
    <!-- Similarly for the XAML editor context menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x0600">  
      <Parent guid="guidXamlUiCmds" id="IDM_XAML_EDITOR" />  
    </CommandPlacement>  
  
  </CommandPlacements>  
  
  <!-- This defines the identifiers and their values used above to index resources  
       and specify commands. -->  
  <Symbols>  
    <!-- This is the package guid. -->  
    <GuidSymbol name="guidColumnGuideCommandsPkg"   
                value="{e914e5de-0851-4904-b361-1a3a9d449704}" />  
  
    <!-- This is the guid used to group the menu commands together -->  
    <GuidSymbol name="guidColumnGuidesCommandSet"   
                value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
      <IDSymbol name="GuidesContextMenuGroup" value="0x1020" />  
      <IDSymbol name="GuidesMenuItemsGroup" value="0x1021" />  
      <IDSymbol name="GuidesSubMenu" value="0x1022" />  
      <IDSymbol name="cmdidAddColumnGuide" value="0x0100" />  
      <IDSymbol name="cmdidRemoveColumnGuide" value="0x0101" />  
      <IDSymbol name="cmdidChooseGuideColor" value="0x0102" />  
      <IDSymbol name="cmdidRemoveAllColumnGuides" value="0x0103" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
      <IDSymbol name="bmpPicAddGuide" value="1" />  
      <IDSymbol name="bmpPicRemoveGuide" value="2" />  
      <IDSymbol name="bmpPicChooseColor" value="3" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp_Dev12"   
                value="{78F03954-2FB8-4087-8CE7-59D71710B3BB}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML_Dev12" value="0x1" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp" value="{d7e8c5e1-bdb8-11d0-9c88-0000f8040a53}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML" value="0x33" />  
      <IDSymbol name="IDMX_HTM_SOURCE_SCRIPT" value="0x34" />  
      <IDSymbol name="IDMX_HTM_SOURCE_ASPX" value="0x35" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidXamlUiCmds" value="{4c87b692-1202-46aa-b64c-ef01faec53da}">  
      <IDSymbol name="IDM_XAML_EDITOR" value="0x103" />  
    </GuidSymbol>  
  </Symbols>  
  
</CommandTable>  
  
```  
  
 **GUID**.  Visual Studio'nın komut işleyicileri bulmak ve onları çağırmak GUID (proje öğesi şablondan oluşturulan) ColumnGuideCommandsPackage.cs dosyasında bildirilen paketi GUID (yukarıda kopyalanır .vsct dosyasında bildirilen paket eşleştiğinden emin olmalısınız. ).  Bu örnek kodunu yeniden kullanırsanız, farklı bir GUID olması böylece herkese ile bu kodu kopyalanan çakışmadığından emin olun.  
  
 İçinde ColumnGuideCommandsPackage.cs Bu satırı bulun ve tırnak işaretleri arasındaki GUID kopyalayın:  
  
```csharp  
public const string PackageGuidString = "ef726849-5447-4f73-8de5-01b9e930f7cd";  
```  
  
 Böylece aşağıdaki satırı sahip GUID .vsct dosyaya yapıştırın, `Symbols` bildirimleri:  
  
```xml  
<GuidSymbol name="guidColumnGuideCommandsPkg"   
            value="{ef726849-5447-4f73-8de5-01b9e930f7cd}" />  
```  
  
 Komut GUID'lerini ayarlayabilir ve bit eşlem resim dosyası çok uzantılarınızın için benzersiz olması gerekir:  
  
```xml  
<GuidSymbol name="guidColumnGuidesCommandSet"   
            value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
<GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
```  
  
 Ancak, komut kümesini değiştirin ve çalışmak için kodu almak için bu kılavuzda görüntü GUID'ler bit eşlem gerekmez.  Ayarla komutu GUID ColumnGuideCommands.cs dosya bildiriminde eşleşmesi gerekiyor, ancak bu dosyanın içeriğini çok yerini alır; Bu nedenle, GUID'ler ile eşleşir.  
  
 Hiçbir zaman değiştirmek için diğer GUID'ler .vsct dosyasındaki sütun kılavuzu komutları eklendiği önceden varolan menülerin tanımlayın.  
  
 **Dosya bölümleri**.  .vsct üç dış bölümü vardır: komutları, yerleşimi ve simgeler.  Komutları bölümüne komut grupları, menüler, düğmeleri veya menü öğeleri ve simgeleri için bit eşlemler tanımlar.  Yerleşimi bölüm grupları menüleri veya önceden varolan menülerin üzerine ek yerleşimi nereye bildirir.  Simgeler bölümü .vsct kod GUID ve onaltılık sayı her yerde sahip değerinden daha okunabilir hale getirir .vsct dosyası başka bir yerde kullanılan tanımlayıcıları bildirir.  
  
 **Komutlar bölümü, tanımları grupları**.  Komutları bölümüne ilk komut gruplarını tanımlar.  Menülerde gruplara ayırarak hafif gri satırıyla bkz komutları komutları gruplarıdır.  Bir grup da bu örnekte olduğu gibi bir tüm alt menü doldurmanız ve bu durumda satırları ayırarak gri görüyor musunuz.  .Vsct dosyaları bildirir iki grup `GuidesMenuItemsGroup` , üst öğe için `IDM_VS_MENU_EDIT` (ana **Düzenle** menüsü) ve `GuidesContextMenuGroup` , üst öğe için `IDM_VS_CTXT_CODEWIN` (kod düzenleyicisinin bağlam menüsü).  
  
 İkinci grup bildirime sahip bir `0x0600` öncelik:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
```  
  
 Sütun yerleştirilecek alt menü alt menü grubunu eklediğimiz olan herhangi bir bağlam menüsündeki sonunda size rehberlik eder olur.  Ancak, en iyi bildiğiniz ve önceliği kullanarak her zaman son olacak şekilde alt menü zorla varsayımında bulunmamalıdır `0xFFFF`.  Alt menü yerleştirdiğiniz burada bağlam menülerini üzerinde nerede arasındadır görmek için bu sayıyı oynamak gerekir.  Bu durumda `0x0600` görebiliriz, ancak kendi uzantısı, arzu ise sütun kılavuzları uzantısı düşük olacak şekilde tasarlayın başka birisi için yeriniz bırakır kadar menüleri sonunda koymak için yüksek.  
  
 **Komutları bölümünde, menü tanımının**.  Alt menü komutu bölümüne sonraki tanımlar `GuidesSubMenu`, üst öğeye sahip için `GuidesContextMenuGroup`.  `GuidesContextMenuGroup` İçin tüm ilgili bağlam menülerini eklediğimiz grubudur.  Yerleşimi bölümünde kodu grubu dört sütun kılavuzu komutları ile bu alt menüsünde yerleştirir.  
  
 **Komutlar bölümü, tanımları düğmeleri**.  Komutları bölümüne sonra menü öğelerini tanımlayan veya komutları dört sütununda düğmeleri size yol gösterir.  `CommandWellOnly`, yukarıda açıklanan, komutları bir ana menüsündeki yerleştirildiğinde görünmez anlamına gelir.  Menü öğesinin iki düğme bildirimleri (Kılavuzu ekleyip Kılavuzu) de bir `AllowParams` bayrağı:  
  
```xml  
<CommandFlag>AllowParams</CommandFlag>  
```  
  
 Bu bayrak, bunların ana menü yerleşimi, Visual Studio komut işleyici istediğinde bağımsız değişkenleri almak için komut sahip ile sağlar.  Kullanıcı komut penceresinde komut çağırırsa, bağımsız değişken komut işleyici olay bağımsız değişken geçirildi.  
  
 **Komutunu bölümleri, bit eşlemler tanımları**.  Son olarak bit eşlemler veya komutlar için kullanılan simgeler komutları bölümüne bildirir.  Bu proje kaynağı tanımlar ve kullanılan simgeler dizinlerini tabanlı listeler basit bir bildirimidir.  Simgeler bölümü .vsct dosyasının dizin kullanılan tanımlayıcıları değerlerini bildirir.  Bu kılavuzda projeye eklenen özel komut öğe şablonu ile sağlanan bit eşlem Şerit kullanır.  
  
 **Yerleşimi bölüm**.  Komutlarından sonra bölümü yerleşimi bölümdür.  Burada, açıklanan ilk grup dört sütun Kılavuzu alt menü komutlarına komutları göründüğü tutan kod ekler ilk sağlayıcıdır:  
  
```xml  
<CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                  priority="0x0100">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
</CommandPlacement>  
```  
  
 Tüm diğer yerleşimi eklemek `GuidesContextMenuGroup` (içeren `GuidesSubMenu`) diğer Düzenleyicisi bağlam menülerini için.  Ne zaman kodu bildirilen `GuidesContextMenuGroup`, kod düzenleyicisinin bağlam menüsü için üst öğe.  Kod Düzenleyicisi'nin içerik menüsü yerleştirme görüyor musunuz nedeni budur.  
  
 **Simge bölüm**.  Yukarıda belirtildiği gibi simgeler bölümü .vsct kod GUID ve onaltılık sayı her yerde sahip değerinden daha okunabilir hale getirir .vsct dosyası başka bir yerde kullanılan tanımlayıcıları bildirir.  Bu bölümdeki önemli noktaları paket GUID'ini GUID komut uygulama sınıfı bildiriminde ile kabul etmeniz gerekir bildirimiyle paket sınıfı ve komut kümesini kabul etmelisiniz edilir.  
  
## <a name="implementing-the-commands"></a>Komutları uygulama  
 ColumnGuideCommands.cs dosya komutları uygular ve işleyicileri kanca oluşturur.  Visual Studio Paketi yükler ve onu başlatır, paket sırayla çağırır `Initialize` komutları uygulama sınıfı.  Komutları başlatma yalnızca sınıfı başlatır ve Oluşturucusu tüm komut işleyicileri kanca oluşturur.  
  
 ColumnGuideCommands.cs dosyasının içeriğini (aşağıda açıklanmıştır) aşağıdaki kodla değiştirin:  
  
```csharp  
using System;  
using System.ComponentModel.Design;  
using System.Globalization;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
using Microsoft.VisualStudio.Text.Editor;  
using Microsoft.VisualStudio;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Command handler  
    /// </summary>  
    internal sealed class ColumnGuideCommands  
    {  
  
        const int cmdidAddColumnGuide = 0x0100;  
        const int cmdidRemoveColumnGuide = 0x0101;  
        const int cmdidChooseGuideColor = 0x0102;  
        const int cmdidRemoveAllColumnGuides = 0x0103;  
  
        /// <summary>  
        /// Command menu group (command set GUID).  
        /// </summary>  
        static readonly Guid CommandSet =   
            new Guid("c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e");  
  
        /// <summary>  
        /// VS Package that provides this command, not null.  
        /// </summary>  
        private readonly Package package;  
  
        OleMenuCommand _addGuidelineCommand;  
        OleMenuCommand _removeGuidelineCommand;  
  
        /// <summary>  
        /// Initializes the singleton instance of the command.  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        public static void Initialize(Package package)  
        {  
            Instance = new ColumnGuideCommands(package);  
        }  
  
        /// <summary>  
        /// Gets the instance of the command.  
        /// </summary>  
        public static ColumnGuideCommands Instance  
        {  
            get;  
            private set;  
        }  
  
        /// <summary>  
        /// Initializes a new instance of the <see cref="ColumnGuideCommands"/> class.  
        /// Adds our command handlers for menu (commands must exist in the command   
        /// table file)  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        private ColumnGuideCommands(Package package)  
        {  
            if (package == null)  
            {  
                throw new ArgumentNullException("package");  
            }  
  
            this.package = package;  
  
            // Add our command handlers for menu (commands must exist in the .vsct file)  
  
            OleMenuCommandService commandService =  
                this.ServiceProvider.GetService(typeof(IMenuCommandService))  
                    as OleMenuCommandService;  
            if (commandService != null)  
            {  
                // Add guide  
                _addGuidelineCommand =   
                    new OleMenuCommand(AddColumnGuideExecuted, null,  
                                       AddColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidAddColumnGuide));  
                _addGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_addGuidelineCommand);  
                // Remove guide  
                _removeGuidelineCommand =  
                    new OleMenuCommand(RemoveColumnGuideExecuted, null,  
                                       RemoveColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidRemoveColumnGuide));  
                _removeGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_removeGuidelineCommand);  
                // Choose color  
                commandService.AddCommand(  
                    new MenuCommand(ChooseGuideColorExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidChooseGuideColor)));  
                // Remove all  
                commandService.AddCommand(  
                    new MenuCommand(RemoveAllGuidelinesExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidRemoveAllColumnGuides)));  
            }  
        }  
  
        /// <summary>  
        /// Gets the service provider from the owner package.  
        /// </summary>  
        private IServiceProvider ServiceProvider  
        {  
            get  
            {  
                return this.package;  
            }  
        }  
  
        private void AddColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _addGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanAddGuideline(currentColumn);  
        }  
  
        private void RemoveColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _removeGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanRemoveGuideline(currentColumn);  
        }  
  
        private int GetCurrentEditorColumn()  
        {  
            IVsTextView view = GetActiveTextView();  
            if (view == null)  
            {  
                return -1;  
            }  
  
            try  
            {  
                IWpfTextView textView = GetTextViewFromVsTextView(view);  
                int column = GetCaretColumn(textView);  
  
                // Note: GetCaretColumn returns 0-based positions. Guidelines are 1-based  
                // positions.  
                // However, do not subtract one here since the caret is positioned to the  
                // left of  
                // the given column and the guidelines are positioned to the right. We  
                // want the  
                // guideline to line up with the current caret position. e.g. When the  
                // caret is  
                // at position 1 (zero-based), the status bar says column 2. We want to  
                // add a  
                // guideline for column 1 since that will place the guideline where the  
                // caret is.  
                return column;  
            }  
            catch (InvalidOperationException)  
            {  
                return -1;  
            }  
        }  
  
        /// <summary>  
        /// Find the active text view (if any) in the active document.  
        /// </summary>  
        /// <returns>The IVsTextView of the active view, or null if there is no active  
        /// document or the  
        /// active view in the active document is not a text view.</returns>  
        private IVsTextView GetActiveTextView()  
        {  
            IVsMonitorSelection selection =  
                this.ServiceProvider.GetService(typeof(IVsMonitorSelection))  
                                                    as IVsMonitorSelection;  
            object frameObj = null;  
            ErrorHandler.ThrowOnFailure(  
                selection.GetCurrentElementValue(  
                    (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame, out frameObj));  
  
            IVsWindowFrame frame = frameObj as IVsWindowFrame;  
            if (frame == null)  
            {  
                return null;  
            }  
  
            return GetActiveView(frame);  
        }  
  
        private static IVsTextView GetActiveView(IVsWindowFrame windowFrame)  
        {  
            if (windowFrame == null)  
            {  
                throw new ArgumentException("windowFrame");  
            }  
  
            object pvar;  
            ErrorHandler.ThrowOnFailure(  
                windowFrame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView, out pvar));  
  
            IVsTextView textView = pvar as IVsTextView;  
            if (textView == null)  
            {  
                IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
                if (codeWin != null)  
                {  
                    ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
                }  
            }  
            return textView;  
        }  
  
        private static IWpfTextView GetTextViewFromVsTextView(IVsTextView view)  
        {  
  
            if (view == null)  
            {  
                throw new ArgumentNullException("view");  
            }  
  
            IVsUserData userData = view as IVsUserData;  
            if (userData == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            object objTextViewHost;  
            if (VSConstants.S_OK  
                   != userData.GetData(Microsoft.VisualStudio  
                                                .Editor  
                                                .DefGuidList.guidIWpfTextViewHost,  
                                       out objTextViewHost))  
            {  
                throw new InvalidOperationException();  
            }  
  
            IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
            if (textViewHost == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            return textViewHost.TextView;  
        }  
  
        /// <summary>  
        /// Given an IWpfTextView, find the position of the caret and report its column  
        /// number. The column number is 0-based  
        /// </summary>  
        /// <param name="textView">The text view containing the caret</param>  
        /// <returns>The column number of the caret's position. When the caret is at the  
        /// leftmost column, the return value is zero.</returns>  
        private static int GetCaretColumn(IWpfTextView textView)  
        {  
            // This is the code the editor uses to populate the status bar.  
            Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
                textView.Caret.ContainingTextViewLine;  
            double columnWidth = textView.FormattedLineSource.ColumnWidth;  
            return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                       / columnWidth));  
        }  
  
        /// <summary>  
        /// Determine the applicable column number for an add or remove command.  
        /// The column is parsed from command arguments, if present. Otherwise  
        /// the current position of the caret is used to determine the column.  
        /// </summary>  
        /// <param name="e">Event args passed to the command handler.</param>  
        /// <returns>The column number. May be negative to indicate the column number is  
        /// unavailable.</returns>  
        /// <exception cref="ArgumentException">The column number parsed from event args  
        /// was not a valid integer.</exception>  
        private int GetApplicableColumn(EventArgs e)  
        {  
            var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
            if (!string.IsNullOrEmpty(inValue))  
            {  
                int column;  
                if (!int.TryParse(inValue, out column) || column < 0)  
                    throw new ArgumentException("Invalid column");  
                return column;  
            }  
  
            return GetCurrentEditorColumn();  
        }  
  
        /// <summary>  
        /// This function is the callback used to execute a command when the a menu item  
        /// is clicked. See the Initialize method to see how the menu item is associated  
        /// to this function using the OleMenuCommandService service and the MenuCommand  
        /// class.  
        /// </summary>  
        private void AddColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.AddGuideline(column);  
            }  
        }  
  
        private void RemoveColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.RemoveGuideline(column);  
            }  
        }  
  
        private void RemoveAllGuidelinesExecuted(object sender, EventArgs e)  
        {  
            GuidesSettingsManager.RemoveAllGuidelines();  
        }  
  
        private void ChooseGuideColorExecuted(object sender, EventArgs e)  
        {  
            System.Windows.Media.Color color = GuidesSettingsManager.GuidelinesColor;  
  
            using (System.Windows.Forms.ColorDialog picker =   
                new System.Windows.Forms.ColorDialog())  
            {  
                picker.Color = System.Drawing.Color.FromArgb(255, color.R, color.G,  
                                                             color.B);  
                if (picker.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
                {  
                    GuidesSettingsManager.GuidelinesColor =   
                        System.Windows.Media.Color.FromRgb(picker.Color.R,  
                                                           picker.Color.G,   
                                                           picker.Color.B);  
                }  
            }  
        }  
  
    }  
}  
  
```  
  
 **Başvuruları düzeltmek**.  Bu noktada bir başvuru eksik.  Çözüm Gezgini'nde başvuruları düğümde sağ işaretçi düğmesine basın.  Seçin **Ekle...**  komutu.  **Başvuru Ekle** iletişim sağ üst köşesinde arama kutusuna sahip.  "Düzenleyicisi" ' (çift tırnak işaretleri olmadan) girin.  Seçin **Microsoft.VisualStudio.Editor** (kontrol gerekir kutunun sol öğenin, yalnızca select öğesi) öğesi ve **Tamam** başvuru eklemek için.  
  
 **Başlatma**.  Paket sınıfı başlatır, çağıran `Initialize` komutları uygulama sınıfı.  `ColumnGuideCommands` Başlatma sınıfı başlatır ve sınıf örneği ve paket başvuru sınıfı üyeleri kaydeder.  
  
 Bir komut işleyici kanca ups at sınıf oluşturucudan bakalım:  
  
```csharp  
_addGuidelineCommand =   
    new OleMenuCommand(AddColumnGuideExecuted, null,  
                       AddColumnGuideBeforeQueryStatus,  
                       new CommandID(ColumnGuideCommands.CommandSet,  
                                     cmdidAddColumnGuide));  
  
```  
  
 Oluşturduğunuz bir `OleMenuCommand`.  Visual Studio, Microsoft Office komut sistemi kullanır.  Bir OleMenuCommand başlatmasını komutu uygulayan işlevi bulunduğunda anahtar bağımsız değişkenler (`AddColumnGuideExecuted`), Visual Studio menü komutu ile gösterdiğinde çağrılacak işlevi (`AddColumnGuideBeforeQueryStatus`) ve komut kimliği.  Visual studio komut kendisini görünmez ya da belirli bir ekran menüsünün için gri yapabilen bir komut menüde gösterilmeden önce sorgu durumu işlevi çağırır (örneğin, devre dışı bırakma **kopyalama** herhangi bir seçim ise), alt simge veya hatta adını (örneğin, eklemek için bir şeyler bir şey Kaldır) değiştirmek ve benzeri.  Komut kimliği .vsct dosyasında bildirilen Komut Kimliği eşleşmesi gerekir.  Komutu için dizeleri ayarlayın ve sütun kılavuzları komutu .vsct dosya ve ColumnGuideCommands.cs arasında eşleşmelidir ekleyin.  
  
 Kullanıcılar (aşağıda açıklanmıştır) komut penceresi aracılığıyla komut çağırdığınızda aşağıdaki satırı Yardım için sağlar:  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
```  
  
 **Sorgu durumu**.  Sorgu durumu işlevleri `AddColumnGuideBeforeQueryStatus` ve `RemoveColumnGuideBeforeQueryStatus` bazı ayarları (örneğin, maksimum sayı kılavuzları veya max sütun) kontrol edin veya kaldırmak için bir sütun kılavuzu ise.  Koşullar doğru olduğunda bunlar komutları etkinleştirin.  Sorgu durumu işlevleri, Visual Studio menüsünde her komut için bir menü gösterir her zaman çalıştıkları çok verimli olması gerekir.  
  
 **AddColumnGuideExecuted işlevi**.  Bir kılavuzu ekleme ilginç bölümü geçerli Düzenleyicisi'ni görüntüleyin ve düzeltme işareti konumunu çıkarılıyor.  Önce bu işlevi çağırır `GetApplicableColumn` komutu işleyicinin olay bağımsız değişkeninde bir kullanıcı tarafından sağlanan bağımsız değişkeni yoktur ve varsa hiçbiri, işlev Düzenleyicisi'nin Görünüm denetler denetler:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
    return GetCurrentEditorColumn();  
}  
  
```  
  
 `GetCurrentEditorColumn` biraz almak için araştırma yapmak sahip bir <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> kod görünümü.  Aracılığıyla izleme varsa `GetActiveTextView`, `GetActiveView`, ve `GetTextViewFromVsTextView`, bunun nasıl yapılacağını görebilirsiniz.  Geçerli seçim ile başlayan seçimin çerçeve alma sonra çerçeve DocView olarak alma soyutlanır, ilgili kodu verilmiştir bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>, ardından alınırken bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> IVsTextView silip bir görünüm konak alma ve Son olarak IWpfTextView:  
  
```csharp  
   IVsMonitorSelection selection =  
       this.ServiceProvider.GetService(typeof(IVsMonitorSelection))   
           as IVsMonitorSelection;  
   object frameObj = null;  
  
ErrorHandler.ThrowOnFailure(selection.GetCurrentElementValue(  
                                (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame,  
                                out frameObj));  
  
   IVsWindowFrame frame = frameObj as IVsWindowFrame;  
   if (frame == null)  
       <<do nothing>>;  
  
...  
   object pvar;  
   ErrorHandler.ThrowOnFailure(frame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView,  
                                                  out pvar));  
  
   IVsTextView textView = pvar as IVsTextView;  
   if (textView == null)  
   {  
       IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
       if (codeWin != null)  
       {  
           ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
       }  
   }  
  
...  
   if (textView == null)  
       <<do nothing>>  
  
   IVsUserData userData = textView as IVsUserData;  
   if (userData == null)  
       <<do nothing>>  
  
   object objTextViewHost;  
   if (VSConstants.S_OK   
           != userData.GetData(Microsoft.VisualStudio.Editor.DefGuidList  
                                                            .guidIWpfTextViewHost,  
                                out objTextViewHost))  
   {  
       <<do nothing>>  
   }  
  
   IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
   if (textViewHost == null)  
       <<do nothing>>  
  
   IWpfTextView textView = textViewHost.TextView;  
  
```  
  
 Bir IWpfTextView olduktan sonra düzeltme işareti bulunduğu sütun alabilirsiniz:  
  
```csharp  
private static int GetCaretColumn(IWpfTextView textView)  
{  
    // This is the code the editor uses to populate the status bar.  
    Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
        textView.Caret.ContainingTextViewLine;  
    double columnWidth = textView.FormattedLineSource.ColumnWidth;  
    return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                / columnWidth));  
}  
  
```  
  
 Kullanıcı tıklattınız burada geçerli sütunla ele kod yalnızca eklemek veya sütunu kaldırmak için ayarları Yöneticisi çağırır.  Ayarlar Yöneticisi için tüm olay harekete `ColumnGuideAdornment` nesneleri dinleme.  Olay başlatıldığında, bu nesnelerin kendi ilişkili metin görünümler yeni sütun kılavuzu ayarlarıyla güncelleştirin.  
  
## <a name="invoking-command-from-the-command-window"></a>Komut penceresinde bildirilecekse komutu  
 Sütun kılavuzları örnek komut penceresinde iki komutları genişletilebilirlik form olarak çağırmak kullanıcıların sağlar.  Kullanırsanız **Görünüm &#124; diğer pencereler &#124; komut penceresi** komutu, komut penceresinde görebilirsiniz.  "Düzenle" girerek komut penceresi ile etkileşim kurabilir ve komut adı tamamlama ve 120 bağımsız değişkeni sağladığını ile aşağıdakilere sahip:  
  
```  
> Edit.AddColumnGuide 120  
>  
```  
  
 Bu öğeler .vsct dosya bildirimlerden etkinleştirmek örnek parçalarını `ColumnGuideCommands` komut işleyicileri ve olay bağımsız denetleyin komut işleyicisi uygulamaları kancalarını zaman sınıfı oluşturucusu.  
  
 Gördüğünüz "`<CommandFlag>CommandWellOnly</CommandFlag>`".vsct dosya yanı sıra düzenleme ana menüdeki yerleşimi rağmen değil gösteriyoruz komutlar **Düzenle** menü UI.  Ana Düzenle menüsünde sahip verir bunları gibi adları **Edit.AddColumnGuide**.  Komutları Düzen menüsünden Grup dört komutları doğrudan yerleştirilen tutan bildirimi Grup:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
```  
  
 Düğmeleri bölümünü daha sonra komutları bildirilen `CommandWellOnly` bunları ana menüde görünmez tutmak için ve bunlarla bildirilen `AllowParams`:  
  
```xml  
<Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
        priority="0x0100" type="Button">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
  <Icon guid="guidImages" id="bmpPicAddGuide" />  
  <CommandFlag>CommandWellOnly</CommandFlag>  
  <CommandFlag>AllowParams</CommandFlag>  
  
```  
  
 Kodda bağlanacağını komut işleyici gördüğünüz `ColumnGuideCommands` sınıfı oluşturucusu sağlanan izin verilen parametre açıklaması:  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
  
```  
  
 Gördüğünüz `GetApplicableColumn` işlev denetimleri `OleMenuCmdEventArgs` Düzenleyicisi'nin görünümü geçerli bir sütun için iade etmeden önce bir değer için:  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
```  
  
## <a name="trying-your-extension"></a>Uzantınızı çalışıyor  
 Şimdi basabilirsiniz **F5** sütun kılavuzları uzantınızı yürütülecek.  Bir metin dosyasını açın ve kılavuz çizgileri eklemek, bunları kaldırmanız ve bunların rengini değiştirmek için düzenleyici bağlam menüsünü kullanın.  Metin tıklamanız gerekir (boşluk değil, satırın sonuna geçirilen) bir sütun eklemek için kılavuzu veya Düzenleyicisi satırındaki son sütun ekler.  Komut penceresinde kullanırsanız ve bir bağımsız değişken komutlarıyla çağırma, herhangi bir yere sütun kılavuzları ekleyebilirsiniz.  
  
 Farklı komut yerleşimi deneyin, adlarını değiştirmek, simgeler ve benzeri değiştirmek istediğiniz ve en son kodu menülerde gösteren Visual Studio ile herhangi bir sorun varsa, hata ayıklama yaptığınız Deneysel hive sıfırlayabilirsiniz.  Ortaya çıkarmak **Windows Başlat menüsü** ve "sıfırlama" yazın.  Arayın ve komut çağırma **sonraki Visual Studio deneysel örneği sıfırlama**.  Bu, tüm Uzantısı bileşenlerini Deneysel kayıt defteri kovanı temizler.  Yok temiz ayarları Bileşenler'den, böylece sahip olduğunuz Visual Studio'nun Deneysel hive kapattığınızda kılavuzları çıkarılsın vardır kodunuzun bir sonraki başlatma ayarları deponuzu okuduğunda.  
  
## <a name="finished-code-project"></a>Tamamlanmış kod projesini  
 Ayrıca Visual Studio genişletilebilirliğini örnekleri github proje yakında olacaktır ve projeyi devam eder.  Bu durum oluştuğunda var. işaret etmek için bu konuda güncelleştireceğiz.  Tamamlanan örnek proje farklı GUID'ler olabilir ve farklı bit eşlemler Şerit komut simgeleri için gerekir.  
  
 Bu Visual Studio Galerisi sütun kılavuzları özelliğiyle sürümü deneyebilirsiniz[uzantısı](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde Düzenleyicisi](../extensibility/inside-the-editor.md)   
 [Düzenleyici ve dil Hizmetleri genişletme](../extensibility/extending-the-editor-and-language-services.md)   
 [Dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)   
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)   
 [Bir menüye alt menü ekleme](../extensibility/adding-a-submenu-to-a-menu.md)   
 [Düzenleyici Öğesi Şablonuyla Uzantı Oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)
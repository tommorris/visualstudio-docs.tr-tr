---
title: Çözüm Gezgini filtre genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Solution Explorer, extending
- extensibility [Visual Studio], projects and solutions
ms.assetid: df976c76-27ec-4f00-ab6d-a26a745dc6c7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 890c3572bf556b92481be204f947b62e6d596264
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135525"
---
# <a name="extending-the-solution-explorer-filter"></a>Çözüm Gezgini filtre genişletme
Genişletebilirsiniz **Çözüm Gezgini** filtre farklı dosyaları gösterme veya gizleme için işlevselliği. Örneğin, yalnızca C# sınıfı Fabrika dosyalarını gösteren bir filtre oluşturabilirsiniz **Çözüm Gezgini**gibi Bu anlatımda gösterilir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="create-a-visual-studio-package-project"></a>Visual Studio Paketi projesi oluşturma  
  
1.  Adlı VSIX proje oluşturma `FileFilter`. Adlı bir özel komut öğesi şablonu Ekle **FileFilter**. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Bir başvuru ekleyin `System.ComponentModel.Composition` ve `Microsoft.VisualStudio.Utilities`.  
  
3.  Menü komutu görünür yapmak **Çözüm Gezgini** araç. FileFilterPackage.vsct dosyasını açın.  
  
4.  Değişiklik `<Button>` aşağıdaki engelle:  
  
    ```xml  
    <Button guid="guidFileFilterPackageCmdSet" id="FileFilterId" priority="0x0400" type="Button">  
        <Parent guid="guidSHLMainMenu" id="IDG_VS_TOOLBAR_PROJWIN_FILTERS" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>FileNameFilter</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
### <a name="update-the-manifest-file"></a>Bildirim dosyasını güncelleştirme  
  
1.  Source.extension.vsixmanifest dosyasında bir MEF bileşen olan bir varlık ekleyin.  
  
2.  Üzerinde **varlıklar** sekmesinde, seçin **yeni** düğmesi.  
  
3.  İçinde **türü** alan, seçin **Microsoft.VisualStudio.MefComponent**.  
  
4.  İçinde **kaynak** alan, seçin **geçerli çözümdeki bir proje ile**.  
  
5.  İçinde **proje** alan, seçin **FileFilter**ve ardından **Tamam** düğmesi.  
  
### <a name="add-the-filter-code"></a>Filtre kodu ekleyin  
  
1.  Bazı GUID'ler FileFilterPackageGuids.cs dosyasına ekleyin:  
  
    ```csharp  
    public const string guidFileFilterPackageCmdSetString = "00000000-0000-0000-0000-00000000"; // get your GUID from the .vsct file  
    public const int FileFilterId = 0x100;  
    ```  
  
2.  Bir sınıf dosyası FileNameFilter.cs adlı FileFilter projeye ekleyin.  
  
3.  Boş ad alanını ve boş sınıfı aşağıdaki kodla değiştirin.  
  
     `Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem rootItems)` Yöntemi çözümü kökündeki içeren koleksiyonu alır (`rootItems`) ve filtreye dahil edilecek öğeleri koleksiyonu döndürür.  
  
     `ShouldIncludeInFilter` Yöntemi filtreler öğeleri **Çözüm Gezgini** hiyerarşi belirttiğiniz koşuluyla tabanlı.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Text.RegularExpressions;  
    using System.Threading.Tasks;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
  
    namespace FileFilter  
    {  
        // Implements ISolutionTreeFilterProvider. The SolutionTreeFilterProvider attribute declares it as a MEF component  
        [SolutionTreeFilterProvider(FileFilterPackageGuids.guidFileFilterPackageCmdSetString, (uint)(FileFilterPackageGuids.FileFilterId))]  
        public sealed class FileNameFilterProvider : HierarchyTreeFilterProvider  
        {  
            SVsServiceProvider svcProvider;  
            IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
            // Constructor required for MEF composition  
            [ImportingConstructor]  
            public FileNameFilterProvider(SVsServiceProvider serviceProvider, IVsHierarchyItemCollectionProvider hierarchyCollectionProvider)  
            {  
                this.svcProvider = serviceProvider;  
                this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
            }  
  
            // Returns an instance of Create filter class.  
            protected override HierarchyTreeFilter CreateFilter()  
            {  
                return new FileNameFilter(this.svcProvider, this.hierarchyCollectionProvider, FileNamePattern);  
            }  
  
            // Regex pattern for CSharp factory classes  
            private const string FileNamePattern = @"\w*factory\w*(.cs$)";  
  
            // Implementation of file filtering  
            private sealed class FileNameFilter : HierarchyTreeFilter  
            {  
                private readonly Regex regexp;  
                private readonly IServiceProvider svcProvider;  
                private readonly IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
                public FileNameFilter(  
                    IServiceProvider serviceProvider,  
                    IVsHierarchyItemCollectionProvider hierarchyCollectionProvider,  
                    string fileNamePattern)  
                {  
                    this.svcProvider = serviceProvider;  
                    this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
                    this.regexp = new Regex(fileNamePattern, RegexOptions.IgnoreCase);  
                }  
  
                // Gets the items to be included from this filter provider.   
                // rootItems is a collection that contains the root of your solution  
                // Returns a collection of items to be included as part of the filter  
                protected override async Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem> rootItems)  
                {  
                    IVsHierarchyItem root = HierarchyUtilities.FindCommonAncestor(rootItems);  
                    IReadOnlyObservableSet<IVsHierarchyItem> sourceItems;  
                    sourceItems = await hierarchyCollectionProvider.GetDescendantsAsync(  
                                        root.HierarchyIdentity.NestedHierarchy,  
                                        CancellationToken);  
  
                    IFilteredHierarchyItemSet includedItems = await hierarchyCollectionProvider.GetFilteredHierarchyItemsAsync(  
                        sourceItems,  
                        ShouldIncludeInFilter,  
                        CancellationToken);  
                    return includedItems;  
                }  
  
                // Returns true if filters hierarchy item name for given filter; otherwise, false</returns>  
                private bool ShouldIncludeInFilter(IVsHierarchyItem hierarchyItem)  
                {  
                    if (hierarchyItem == null)  
                    {  
                        return false;  
                    }  
                    return this.regexp.IsMatch(hierarchyItem.Text);  
                }  
            }  
        }  
    }  
  
    ```  
  
4.  FileFilter.cs içinde komut yerleştirme ve işleme kodu FileFilter oluşturucudan kaldırın. Sonuç aşağıdaki gibi görünmelidir:  
  
    ```csharp  
    private FileFilter(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
    }  
    ```  
  
     ShowMessageBox() yöntemi de kaldırın.  
  
5.  FileFilterPackage, cs, önce Initialize() yöntemini kodda aşağıdakiyle değiştirin:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        Debug.WriteLine (string.Format(CultureInfo.CurrentCulture, "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
    }  
    ```  
  
### <a name="test-your-code"></a>Kodunuzu test  
  
1.  Oluşturun ve projeyi çalıştırın. Visual Studio ikinci bir örneğini görüntülenir. Bu deneysel örneği denir.  
  
2.  Visual Studio deneysel örneğinde bir C# projesini açın.  
  
3.  Çözüm Gezgini araç çubuğunda eklenen düğmesi arayın. Sol dördüncü düğmesinden olmalıdır.  
  
4.  Düğmeye tıkladığınızda, tüm dosyaları filtrelenmelidir ve "tüm öğeler görünümünden filtrelendi." görmeniz gerekir Çözüm Gezgini'nde.
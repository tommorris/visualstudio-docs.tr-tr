# <a name="updating-an-existing-application-for-msbuild-15"></a>Varolan bir uygulama için MSBuild 15 güncelleştiriliyor

MSBuild sürümlerinde 15.0 önce Genel Derleme Önbelleği (GAC) MSBuild yüklendi ve MSBuild uzantıları kayıt defterinde yüklendi. Bu, tüm uygulamaları kullanılan MSBuild aynı sürümü ve aynı toolsets erişebildiği ancak farklı Visual Studio sürümlerini yan yana yüklemesini engelleyen güvence altına.

Daha hızlı ve daha küçük ve yan yana yükleme desteklemek için Visual Studio 2017 artık MSBuild GAC'ye yerleştirir veya kayıt defteri değiştirir. Ne yazık ki, bu MSBuild API değerlendirmek veya projeler derlemek için kullanmak istediğiniz uygulamaların Visual Studio yükleme örtük olarak kullanan olamaz anlamına gelir.

## <a name="using-msbuild-from-visual-studio"></a>Visual Studio'dan MSBuild kullanma

Uygulamanızdan programlı derlemeleri Visual Studio veya MSBuild.exe içinde yapılan eşleştiğinden emin olmak için Visual Studio'dan MSBuild derlemeleri yükleyin ve Visual Studio içinde kullanılabilir SDK'ları kullanın. Microsoft.Build.Locator NuGet paketi bu işlemi kolaylaştırır.

## <a name="using-microsoftbuildlocator"></a>Microsoft.Build.Locator kullanma

Dağıtırsanız `Microsoft.Build.Locator.dll` uygulamanızla birlikte diğer MSBuild derlemelerini dağıtmak gerekmez.

MSBuild 15 ve API Bulucu kullanmak üzere bir proje güncelleştirme, aşağıda açıklanan projenizdeki bazı değişiklikler gerektirir. Örnek Proje güncelleştirmek için gereken değişiklikleri görmek için bkz: [MSBuildLocator depo örnek projesinde yapılan işlemeleri](https://github.com/Microsoft/MSBuildLocator/commits/example-updating-to-msbuild-15).

### <a name="change-msbuild-references"></a>MSBuild başvuruları değiştirme

MSBuild merkezi bir konumdan yüklendiğinden emin olmak için kendi derlemeler uygulamanızla birlikte dağıtmalısınız değil.

MSBuild merkezi bir konumdan yüklenmesini önlemek için projenizi değiştirmek için mekanizması MSBuild nasıl başvuru bağlıdır.

#### <a name="using-nuget-packages-preferred"></a>NuGet paketlerini (tercih edilen) kullanma

Bu yönergeler, kullanmakta olduğunuz varsayılmıştır [ `PackageReference`-NuGet başvurularını stil](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files).

MSBuild derlemeleri kendi NuGet paketleri başvurmak için proje dosyalarınız değiştirin. Belirtin `ExcludeAssets=runtime` derlemeler yalnızca derleme zamanında gereklidir ve çıktı dizinine kopyalanmaması gereken NuGet bildirmek için.

MSBuild paketlerin birincil ve ikincil sürüm Visual Studio, desteklemek istediğiniz minimum sürümüne eşit veya daha az olmalıdır. Visual Studio 2017 herhangi bir sürümünü desteklemek istiyorsanız, Paket sürümü başvuru `15.1.548`.

Örneğin, bu XML kullanabilirsiniz:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Build" Version="15.1.548" ExcludeAssets="runtime" />
  <PackageReference Include="Microsoft.Build.Utilities" Version="15.1.548" ExcludeAssets="runtime" />
</ItemGroup>
```

#### <a name="using-extension-assemblies"></a>Uzantı derlemeler kullanma

NuGet paketlerini kullanamıyorsanız, Visual Studio ile dağıtılmış MSBuild derlemeleri başvuruda bulunabilir. MSBuild doğrudan başvurursanız, bu çıkış dizininize ayarlayarak kopyalanmaz emin olun `Copy Local` için `False`. Proje dosyasında bu aşağıdaki gibi görünür:

```xml
    <Reference Include="Microsoft.Build, Version=15.1.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL">
      <Private>False</Private>
    </Reference>
```

#### <a name="binding-redirects"></a>Bağlama yeniden yönlendirmeleri

Microsoft.Build.Locator paketini otomatik olarak başvuran sağlar uygulamanızın sürüme MSBuild derlemelerin tüm sürümlerin gerekli bağlama yeniden yönlendirmeleri kullandığı `15.1.0.0`.

### <a name="ensure-output-clean"></a>Çıktı temiz emin olun

Projenizi oluşturun ve onu içermediğinden emin emin olmak için çıktı dizini inceleyin `Microsoft.Build.*.dll` derlemeler (dışında `Microsoft.Build.Locator.dll`, sonraki adımda eklenen).

### <a name="add-package-reference"></a>Paketi Başvurusu Ekle

NuGet paket için bir başvuru ekleyin [Microsoft.Build.Locator](https://www.nuget.org/packages/Microsoft.Build.Locator/).

```xml
    <PackageReference Include="Microsoft.Build.Locator">
      <Version>1.0.7-preview-ge60d679b53</Version>
    </PackageReference>
```

### <a name="register-instance-before-calling-msbuild"></a>MSBuild çağırmadan önce kayıt örneği

MSBuild kullanan herhangi bir yöntemini çağırmadan önce Bulucu API çağrısı ekleyin.

Bunu yapmanın en kolay yolu için bir çağrı eklemektir.

```c#
MSBuildLocator.RegisterDefaults();
```

Uygulama başlangıç kodunuzda.

MSBuild yüklenmesini üzerinde daha hassas denetim isterseniz, bir sonucu seçebilirsiniz `MSBuildLocator.QueryVisualStudioInstances()` geçirilecek `MSBuildLocator.RegisterInstance()` el ile ancak bu genelde gerekli değildir.

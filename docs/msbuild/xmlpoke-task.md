---
title: XmlPoke görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31c76ba53e858d9eab41d6579950f47b16f8c9b8
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056361"
---
# <a name="xmlpoke-task"></a>XmlPoke Görevi

Bir XML dosyasına bir XPath sorgusu tarafından belirtilen değerlerini ayarlar.

## <a name="parameters"></a>Parametreler

 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `XmlPoke` görev.
  
|Parametre|Açıklama|
|---------------|-----------------|
|`Namespaces`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu önekler için ad belirtir. `Namespaces` olan oluşan bir XML parçacığını `Namespace` öznitelikleri öğeleriyle `Prefix` ve `Uri`. Öznitelik `Prefix` belirtilen ad alanı ilişkilendirmek için önek belirtir `Uri` özniteliği. Boş bir kullanmayın `Prefix`.|
|`Query`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu belirtir.|
|`Value`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Belirtilen yola eklenecek değeri belirtir.|
|`XmlInputPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> XML Giriş bir dosya yolu belirtir.|

## <a name="remarks"></a>Açıklamalar

 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Örnek

Değiştirilecek bir örnek.XML şöyledir:

```
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10" >
<Identity Name="Sample.Product " Publisher="CN=1234" Version="1.0.0.0" />
<mp:PhoneIdentity PhoneProductId="456" PhonePublisherId="0" />
</Package>
```

Değişiklik yapmak istiyorsanız bu örnekte, `/Package/mp:PhoneIdentity/PhonePublisherId`, ardından kullanın

```
<Project>
  <PropertyGroup>
    <Namespace>
        <Namespace Prefix="dn" Uri="http://schemas.microsoft.com/appx/manifest/foundation/windows10" />
        <Namespace Prefix="mp" Uri="http://schemas.microsoft.com/appx/2014/phone/manifest" />
        <Namespace Prefix="uap" Uri="http://schemas.microsoft.com/appx/manifest/uap/windows10" />
    </Namespace>
</PropertyGroup>

<Target Name="Poke">
  <XmlPoke
    XmlInputPath="Sample.xml"
    Value="MyId"
    Query="/dn:Package/mp:PhoneIdentity/@PhoneProductId"
    Namespaces="$(Namespace)"/>
</Target>
</Project>
```

`dn` Burada bir yapay ad alanı öneki varsayılan ad alanı için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)

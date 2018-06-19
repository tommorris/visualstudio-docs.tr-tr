---
title: Özel bir NuGet kullanma bağlı bir ortamda akış | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/27/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Özel bir NuGet erişmek ve NuGet paketleri bağlı bir ortamda kullanmak üzere akışı kullanın.
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 71fcf1c3cfb37d783de13514f6a048c3b3711a53
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031227"
---
#  <a name="use-a-custom-nuget-feed-in-a-connected-environment"></a>Bağlı bir ortamda akış özel bir NuGet kullanma

Bir NuGet akışı paket kaynaklarını bir proje eklemek için kolay bir yol sağlar. Bağlı ortam Bu bağımlılıklar Docker kapsayıcısında düzgün bir şekilde yüklenmesi için sırayla akış erişebilmeleri gerekir.

Bir NuGet akış ayarlamak için:
1. Ekleme bir [paketini başvuru](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files) içinde `*.csproj` altında dosya `PackageReference` düğümü.

   ```xml
   <ItemGroup>
       <!-- ... -->
       <PackageReference Include="Contoso.Utility.UsefulStuff" Version="3.6.0" />
       <!-- ... -->
   </ItemGroup>
   ```

2. Oluşturma bir [NuGet.Config](https://docs.microsoft.com/en-us/nuget/reference/nuget-config-file) proje klasöründeki dosya.
     * Kullanım `packageSources` konumu akış, NuGet başvurmak için bölüm. Önemli: NuGet akışı genel olarak erişilebilir olmalıdır.
     * Kullanım `packageSourceCredentials` bölümünde kullanıcı adı ve parola kimlik bilgilerini yapılandırın. 

   ```xml
   <packageSources>
       <add key="Contoso" value="https://contoso.com/packages/" />
   </packageSources>

   <packageSourceCredentials>
       <Contoso>
           <add key="Username" value="user@contoso.com" />
           <add key="ClearTextPassword" value="33f!!lloppa" />
       </Contoso>
   </packageSourceCredentials>
   ```

3. Kaynak kodu denetimi kullanıyorsanız:
    - Başvuru `NuGet.Config` içinde `.gitignore` kimlik bilgilerini kaynak deponuza yanlışlıkla yürütme yok şekilde dosya.
    - Açık `vsce.yaml` dosya projenizde ve bulun `build` bölümünde ve emin olmak için aşağıdaki kod parçacığını ekleyin `NuGet.Config` dosya işlemleri senkronize edilir Azure'a böylece kapsayıcı görüntü oluşturma işlemi sırasında kullanılır. (Varsayılan olarak bağlı ortam eşleşen dosyaları eşitlenmediğini `.gitignore` ve `.dockerignore` kuralları.)

        ```yaml
        build:
        useGitIgnore: true
        ignore:
        - “!NuGet.Config”
        ```


## <a name="next-steps"></a>Sonraki adımlar

Yukarıdaki adımları tamamladıktan sonra bir sonraki defa çalıştırılması `vsce up` (veya isabet `F5` VSCode ya da Visual Studio), bağlı ortam eşitleyecek `NuGet.Config` sonra tarafından kullanılan Azure dosyasına `dotnet restore` paketini yüklemek için kapsayıcı bağımlılıkları.


---
title: Sorun giderme | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 0f35e31e3f3a109e65565592b56b6dc4177dd7c0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

## <a name="error-upstream-connect-error-or-disconnectreset-before-headers"></a>Hata 'upstream bağlantı hatası veya kesin/reset önce üstbilgileri'
Hizmetinize erişmek çalışırken, bu hatayı görebilirsiniz. Örneğin, ne zaman, bir tarayıcıda hizmetin URL'sine gidin. 

**Neden:** kapsayıcı bağlantı noktası kullanılabilir değil. En yaygın nedenleri şunlardır: 
* , Yine yerleşik dağıtılan ve sürecinde kapsayıcıdır. Çalıştırıyorsanız bu durum, `vsce up` veya hata ayıklayıcısını başlatın ve sonra başarıyla dağıtıldığını önce kapsayıcı erişmeyi deneyin.
* Bağlantı noktası yapılandırmasını, Dockerfile, Helm grafik ve bağlantı noktası açar. herhangi bir sunucu kodu arasında tutarlı değil.

**Deneyin:**
1. Kapsayıcı yerleşik/dağıtılan sürecinde ise, 2-3 saniye bekleyin ve hizmet erişimi yeniden deneyin. 
1. Bağlantı noktası yapılandırmanızı denetleyin. Belirtilen bağlantı noktası numaralarını olmalıdır **aynı** aşağıdaki tüm varlıklar içinde:
    * **Dockerfile:** tarafından belirtilen `EXPOSE` yönergesi.
    * **[Helm grafik](https://docs.helm.sh):** tarafından belirtilen `externalPort` ve `internalPort` bir hizmet için değerleri (genellikle bulunan bir `values.yml` dosyası),
    * Örneğin Node.js içinde uygulama kodundaki açılmakta tüm bağlantı noktaları: `var server = app.listen(80, function () {...}`


## <a name="config-file-not-found"></a>Yapılandırma dosyası bulunamadı
Çalıştırmadan `vsce up` ve aşağıdaki hatayı alıyorsunuz: `Config file not found: .../vsce.yaml`

**Neden:** `vsce up` kodu kök dizininden çalıştırmak için çalıştırmak istediğiniz ve kod klasörü bağlı ortamla çalıştırmak için başlatılmış olması gerekiyor.

**Deneyin:**
1. Geçerli dizin hizmeti kodunuzu içeren kök klasör olarak değiştirin. 
1. Kod klasöründe vsce.yaml dosya yoksa çalıştırmak `vsce init` Docker, Kubernetes ve VSCE varlıklar oluşturmak için.

## <a name="error-the-pipe-program-vsce-exited-unexpectedly-with-code-126"></a>Hata: 'kanal programı '126 koduyla beklenmedik biçimde çıktı vsce'.'
VS Code hata ayıklayıcıyı başlatma bazen bu hatasına neden olabilir. Bu bir hatadır.

**Deneyin:**
1. Kapatın ve VS Code'u yeniden açın.
2. F5 yeniden ulaştı.


## <a name="debugging-error-configured-debug-type-coreclr-is-not-supported"></a>'Yapılandırıldı hata ayıklama türü 'coreclr' desteklenmiyor' hata ayıklama
Hata raporlarını VS Code hata ayıklayıcı çalıştırma: `Configured debug type 'coreclr' is not supported.`

**Neden:** bağlı geliştirme makinenizde yüklü ortamınıza VS Code uzantısı yok.

**Deneyin:** yükleme [VS Code uzantısı bağlı ortam için](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code).


## <a name="the-azure-portal-doesnt-show-connected-environment-instances"></a>Azure portalı bağlı ortam örnekleri göstermiyor

**Neden:** bağlı ortam için bir Azure portal deneyimi henüz Önizleme için hazır değil.


## <a name="the-type-or-namespace-name-mylibrary-could-not-be-found"></a>'Kitaplığım' türü veya ad alanı adı bulunamadı

**Neden:** yapı bağlamdır proje/hizmet düzeyinde varsayılan olarak, bu nedenle kullanmakta olduğunuz bir kitaplık projesine bulunamayacaktır.

**Deneyin:** yapılması gerekenler:
1. Yapı bağlamı için çözüm düzeyini ayarlamak için vsce.yaml dosyasını değiştirin.
2. Csproj dosyaları yeni derleme bağlam göre doğru şekilde başvurmak için Dockerfile ve Dockerfile.develop dosyaları değiştirin.
3. .Dockerignore dosya .sln dosyasını yerleştirin ve gerektiği gibi değiştirin.

Bir örneğe bulabilirsiniz https://github.com/sgreenmsft/buildcontextsample

## <a name="microsoftconnectedenvironmentregisteraction-authorization-error-when-creating-an-environment"></a>'Microsoft.ConnectedEnvironment/register/action' authorization error when creating an environment
Bir ortam yönetirken aşağıdaki hatayı görebilirsiniz ve bir Azure aboneliğinin sahibi veya katkıda erişim yok çalışıyoruz.
`The client '<User email/Id>' with object id '<Guid>' does not have authorization to perform action 'Microsoft.ConnectedEnvironment/register/action' over scope '/subscriptions/<Subscription Id>'.`

**Neden:** seçili Azure aboneliği Microsoft.ConnectedEnvironment ad alanı kayıtlı değil.

**Deneyin:** Azure aboneliğinin sahibi veya katkıda erişim biriyle elle Microsoft.ConnectedEnvironment ad alanı kaydetmek için aşağıdaki Azure CLI komutu çalıştırabilirsiniz:

```cmd
az provider register --namespace Microsoft.ConnectedEnvironment
```

## <a name="vsce-doesnt-seem-to-use-my-existing-dockerfile-to-build-a-container"></a>VSCE bir kapsayıcı oluşturmak için varolan my Dockerfile kullanma gibi görünüyor 

**Neden:** VSCE, belirli bir Dockerfile projenizdeki işaret edecek şekilde yapılandırılabilir. VSCE kapsayıcılarınızı yapı beklediğiniz Dockerfile kullanmıyor görünürse, açıkça olduğu VSCE söyleyin gerekebilir. 

**Deneyin:** açık `vsce.yaml` projenizde VSCE tarafından oluşturulan dosya. Kullanmak `configurations->develop->build->dockerfile` yönergesi Dockerfile işaret etmek için kullanmak istediğiniz:

```
...
configurations:
  develop:
    build:
      dockerfile: Dockerfile.develop
```
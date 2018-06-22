---
title: Kubernetes araçları Öğreticisi | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- azure
ms.openlocfilehash: b354045ceb464a14ff909a503aa62477c73b983c
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280883"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>Visual Studio Kubernetes araçları ile çalışmaya başlama

Visual Studio Kubernetes araçları Kubernetes hedefleme kapsayıcılı uygulamalarının geliştirilmesi akıcı hale getirmesine yardımcı olur. Visual Studio Dockerfiles ve Helm grafikler gibi Kubernetes dağıtımını desteklemek için gereken yapılandırma olarak kod dosyaları otomatik olarak oluşturabilirsiniz. Ayrıca, Visual Studio'dan bir Azure Kubernetes hizmet (AKS) kümesine doğrudan yayımlayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu yeni işlevsellik yararlanmak için ihtiyacınız vardır:

- En son önizlemesi [Visual Studio 2017](https://visualstudio.microsoft.com/vs/preview) Azure geliştirme iş yükü ile.

- [Kubernetes araçları Visual Studio için](https://aka.ms/get-vsk8stools), ayrı bir yükleme olarak kullanılabilir.

- [Windows için docker](https://store.docker.com/editions/community/docker-ce-desktop-windows) geliştirme iş istasyonunda yüklü (diğer bir deyişle, Visual Studio çalıştırdığınız)

- Visual Studio'dan AKS için yayımlama istiyorsanız:

    1.  [Yayınlama araçları AKS](https://aka.ms/get-vsk8spublish), ayrı bir yükleme olarak kullanılabilir.

    1.  Azure Kubernetes hizmeti kümesi. Daha fazla bilgi için bkz: [AKS küme oluşturma](/azure/aks/kubernetes-walkthrough-portal#create-aks-cluster). Şunları yaptığınızdan emin olun [kümeye bağlanın](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster) , geliştirme iş istasyonundan.

    1.  Helm CLI geliştirme iş istasyonunda yüklü. Daha fazla bilgi için bkz: [yükleme Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md).

    1.  Helm AKS kümenizi karşı yapılandırılmış. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [Helm yapılandırma](/azure/aks/kubernetes-helm#configure-helm).

## <a name="create-a-new-kubernetes-project"></a>Yeni bir Kubernetes projesi oluşturma

Uygun araçlarının yüklü olduğu olduktan sonra Visual Studio'yu başlatın ve yeni bir proje oluşturun. Altında **bulut**, seçin **Kubernetes için kapsayıcı uygulama** proje türü. Bu proje türü seçip **Tamam**.

![Yeni bir Kubernetes uygulama projesi oluşturma ekran görüntüsü](media/k8s-tools-new-k8s-app.png)

Web uygulaması oluşturmak için ASP.NET Core türünü seçebilirsiniz. Seçin **Web uygulaması** ve **Tamam**. Normal **Docker desteğini etkinleştir** seçeneği bu iletişim kutusunda görüntülenmez.  Docker destek Kubernetes için bir kapsayıcı uygulama için varsayılan olarak etkindir.

![Web uygulaması seçimi ekran görüntüsü](media/k8s-tools-web-app-selection-screen.png)

## <a name="add-kubernetes-support-to-an-existing-project"></a>Varolan bir projeye Kubernetes desteği ekleme

Alternatif olarak, mevcut bir ASP.NET Core web uygulaması projesini Kubernetes destek ekleyebilirsiniz. Bunu yapmak için projeye sağ tıklayın ve seçin **Ekle** > **kapsayıcı Orchestrator Destek**.

![Ekran görüntüsü, ekleme kapsayıcı Orchestrator menü öğesi](media/k8s-tools-add-container-orchestrator.png)

İletişim kutusunda, "Kubernetes/Helm" seçip seçin **Tamam**.

![Ekran görüntüsü, ekleme kapsayıcı Orchestrator iletişim kutusu](media/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Visual Studio sizin için ne oluşturur

Yeni bir oluşturduktan sonra **Kubernetes için kapsayıcı uygulama** , proje veya varolan bir projeye Kubernetes kapsayıcı orchestrator desteği ekleme, kolaylaştırmak için Kubernetes dağıtma bazı ek dosyaları projenizde görürsünüz.

![Ekran görüntüsü, çözüm kapsayıcı Orchestrator destek ekledikten sonra Gezgini](media/k8s-tools-solution-explorer.png)

Eklenen dosyalar şunlardır:

- Bu web uygulamasını barındıran kapsayıcı görüntü bir Docker oluşturmanıza olanak sağlayan bir Dockerfile. Gördüğünüz gibi Visual Studio Araçları hata ayıklama ve Kubernetes için dağıtırken bu Dockerfile yararlanır. Doğrudan Docker görüntü ile çalışmayı tercih ederseniz, Dockerfile sağ tıklatın ve seçin **yapı Docker görüntü**.

   ![Yapı Docker görüntüsü ekran seçeneği](media/k8s-tools-build-docker-image.png)

- Helm grafik ve *grafikleri* klasör. Bu yaml dosyalar için Kubernetes dağıtmak için kullanabileceğiniz uygulama Helm grafik oluşturur. Helm hakkında daha fazla bilgi için bkz: [ https://www.helm.sh ](https://www.helm.sh).

- *azds.yaml*. Bu, Azure Dev alanları, hızlı ve yinelemeli bir hata ayıklama deneyimini Azure Kubernetes hizmetindeki sağlayan yeni bir hizmet ayarlarını içerir. Bu dosya şu anda kullanılmayan, ancak gelecekte kullanılmak üzere Azure Dev boşluklarla ayrılmış.

## <a name="publish-to-azure-kubernetes-service-aks"></a>Azure Kubernetes hizmet (AKS) yayımlama

Yalnızca her zamanki gibi tüm bu dosyaları yerinde, Visual Studio IDE yazmak ve uygulama kodunuzun hatalarını ayıklamak için kullanabilirsiniz.

AKS kümeye doğrudan Visual Studio'dan yayımlamak istediğiniz şekilde çalışan, kodunuzu sahip olduğunda.

Bunu yapmak için ilk Azure kapsayıcı kayıt defteri (ACR) kapsayıcı görüntünüzü yayımlayan bir yayımlama profili ayarlamanız gerekir. Ardından AKS kapsayıcı görüntünüzü ACR çekme ve kümesine dağıtabilirsiniz.

1. İçinde **Çözüm Gezgini**, sağ tıklayın, *proje* ve **Yayımla**.

   ![Menü öğesi, ekran yayımlama](media/k8s-tools-publish-project.png)

1. İçinde **Yayımla** ekranında, seçin **kapsayıcı kayıt defteri** Yayımla olarak hedef ve kapsayıcı kaydınız seçmek için istemleri izleyin. Bir kapsayıcı kayıt defteri yoksa seçin **oluşturma yeni Azure kapsayıcı kayıt defteri** Visual Studio'dan oluşturmak için. Daha fazla bilgi için bkz: [, kapsayıcı Azure kapsayıcı kayıt defterine yayımlama](#publish-your-container-to-azure-container-registry).

   ![Ekran çekme Yayımla hedef ekran görüntüsü](media/k8s-tools-publish-to-acr.png)

1. Geri Çözüm Gezgini'nde sağ tıklayın, *çözüm* tıklatıp **Azure AKS Yayımla**.

   ![Ekran görüntüsü, yayımlamayı Azure AKS menü öğesi](media/k8s-tools-publish-solution.png)

1. Aboneliğiniz ve AKS kümenizi seçin, oluşturduğunuz profil birlikte ACR yayımlama. Sonra **Tamam**'a tıklayın.

   ![Ekran görüntüsü, yayımlamayı AKS ekranı](media/k8s-tools-publish-to-aks.png)

   Bu, olanak sürer **Azure AKS Yayımla** ekran.

1.  Seçin **yapılandırma Helm** Helm grafikleri sunucuya yüklemek için kullanılan komut satırı güncelleştirmek için bağlantı.

   ![Yapılandırma Helm ekran bağlantı](media/k8s-tools-configure-helm.png)

   Komut satırı güncelleştirmek, farklı bir Kubernetes bağlamı veya grafik ad gibi belirtmek istediğiniz özel komut satırı bağımsız değişkenleri varsa yararlı olur.

   ![Screenshoot, Helm ekran yapılandırın](media/k8s-tools-helm-configure-screen.png)

1. Dağıtmaya hazır olduğunuzda tıklatın **Yayımla** AKS uygulamanızı yayımlamak için düğmesi.

   ![Ekran görüntüsü Azure AKS ekranına yayımlama](media/k8s-tools-publish-screen.png)

Tebrikler! Artık tüm Kubernetes uygulama geliştirme için Visual Studio gücünü kullanabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Azure üzerinde Kubernetes geliştirme hakkında daha fazla bilgi okuyarak [AKS belgelerine](/azure/aks).
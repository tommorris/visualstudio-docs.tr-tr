---
title: Bir .NET Core geliştirme ortamı oluşturma - adım 3 - Visual Studio ile bulutta Kubernetes kullanarak kapsayıcıları Kubernetes geliştirme ortamı oluşturma | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 6226340b1744e95bbb375d47213ae00bb9e76565
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Önceki adımda: [ASP.NET web uygulamaları oluşturma](get-started-netcore-visualstudio-02.md)

## <a name="create-a-dev-environment-in-azure"></a>Bir geliştirme ortamı oluşturma
Bağlı bir ortam tamamen Azure tarafından yönetilen ve geliştirme için optimize edilmiş Kubernetes tabanlı geliştirme ortamları oluşturabilirsiniz. Yeni oluşturduğumuz açık projeyle seçin **bağlı ortam AKS için** öğesinden aşağıda gösterildiği gibi başlatma ayarları açılır.

![](images/LaunchSettings.png)

Ardından görüntülenen iletişim kutusunda uygun hesabıyla oturum açmış ve var olan bir geliştirme ortamı seçin ya da emin olun veya seçin **< yeni bağlı ortam oluştur... AKS için >** yeni bir tane oluşturmak için.

![](images/ConnectedEnvDialog.png)

Sağlanan varsayılan değerleri kullanın veya bunları istediğiniz şekilde ayarlayın. Tıklatın **Tamam** değerlerini ayarlandığında uygun şekilde.

![](images/NewEnvDialog.png)

Önceki iletişim kutusunda bırakın **alanı** açılır varsayılan için `mainline` şimdilik, biz bunu daha sonra daha ayrıntılı olarak ele alınacaktır. Denetleme **genel olarak erişilebilir** web uygulaması genel bir uç nokta erişilebilir olması için onay kutusu. Bu gerekli değildir, ancak bu kılavuzda daha sonra bazı kavramları göstermeye yardımcı olacaktır. Ancak endişelenmeyin, her iki durumda da, Visual Studio kullanarak Web sitenizi hata ayıklamak kullanamazsınız.

![](images/ConnectedEnvDialog2.png)

Tıklatın **Tamam** seçmek veya geliştirme ortamı oluşturmak için. Bunu gerçekleştirmek için bir arka plan görevi başlatılır, işlemin tamamlanması gereken dakika sayısını sürecek. Bunu hala imlecinizin üzerine gelerek oluşturuluyor varsa görebilirsiniz **arka plan görevleri** durumu sol alt köşesindeki simgesine çubuğu (aşağıya bakın).

![](images/BackgroundTasks.png)

> [!Note]
Geliştirme ortamı başarıyla oluşturulana kadar uygulamanızda hata ayıklama olamaz.

## <a name="look-at-the-files-added-to-project"></a>Projeye eklenen dosyalar bakın
Biz oluşturulacak geliştirme ortamı için beklerken bir geliştirme ortamı kullanmayı seçtiğinizde, projenize eklenen dosyaları bakalım.

Adlı bir klasör ilk olarak, görebilirsiniz `charts` eklendi ve bu içinde bir [Helm grafik](https://docs.helm.sh) uygulamanız iskele kurulmuş için. Bu dosyalar, geliştirme ortamı uygulamanıza dağıtmak için kullanılır.

Adlı bir dosya görürsünüz `Dockerfile` eklendi. Bu dosyayı standart Docker biçim uygulamanızda paketlemek için gerekli olan bilgiler bulunur. A `HeaderPropagation.cs` dosyası da oluşturulur, bu dosya daha sonra kılavuzda aşağıdakiler ele alınacaktır. 

Son olarak, adında bir dosya görürsünüz `vsce.yaml` gibi olup uygulamanın genel bir uç nokta erişilebilir olmalıdır geliştirme ortamı tarafından gereken yapılandırma bilgilerini içerir.

![](images/ProjectFiles.png)

> [!div class="nextstepaction"]
> [Kubernetes kapsayıcısında hata ayıklama](get-started-netcore-visualstudio-04.md)
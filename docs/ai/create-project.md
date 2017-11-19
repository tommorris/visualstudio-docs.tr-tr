---
title: "AI araçlarında için Visual studio projesi oluşturma"
description: "azure machine learning Galerisi'nden örnek kullanarak proje oluşturma"
keywords: AI, visual studio, azure machine learning
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: how to article
ms.technology: visual studio
ms.devlang: multiple
ms.service: multiple
ms.openlocfilehash: 2d8b5f1d06d31eaba9c75e0f0515b2526fc7efdf
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
## <a name="create-an-ai-project-from-the-azure-machine-learning-gallery-in-visual-studio"></a>Visual Studio'da Azure Machine Learning Galeriden bir AI projesi oluşturma

Azure Machine Learning AI için Visual Studio Araçları ile tümleşiktir. Azure sanal makineler, Spark kümeleri ve daha fazlası gibi uzak işlem hedefleri machine learning iş göndermek için kullanabilirsiniz. Daha fazla bilgi edinmek [Azure Machine Learning deneme](https://docs.microsoft.com/azure/machine-learning/preview/experimentation-service-configuration) 

Seçtiğiniz sonra [AI için Visual Studio Araçları yüklü](installation.md), Azure Machine Learning örnek Galerisi'nde önceden yapılmış tarif kullanarak yeni bir Python proje oluşturmak kolaydır.

> ! Azure Machine Learning çalışma ekranı yüklü olması gerekir. Bkz: Lütfen yüklemek için [Azure Machine Learning yükleme hızlı başlangıç](https://docs.microsoft.com/azure/machine-learning/preview/quickstart-installation) 

1. Visual Studio'yu başlatın. Açık **Sunucu Gezgini** açarak **AI Araçları** menü ve seçme **küme seçin**  

    ![Küme Seçici](media\create-project\select-cluster.png)

1. Azure Machine Learning aboneliğinize sağ tıklayarak oturum açın **Azure Machine Learning** Sunucu Gezgininde seçip **oturum açma** ve yönergeleri izleyin.

    ![oturum açma](media\create-project\azureml-login.png)
 
2. Seçin **AI Araçlar > Azure Machine Learning örnek Galerisi**. 
    
    ![Örnek Galerisi](media\create-project\gallery.png)

1. Bu Hızlı Başlangıç için seçin "**TensorFlow kullanarak MNIST**" örnek ve tıklayın **yükleme**. Sağlayın 
2.
 - **Kaynak grubu**: meta verilerinizin depolanacağı Azure kaynak grubu
 - **Hesap**: Azure Machine Learning deneme hesabı
 - **Çalışma alanı**: Azure Machine Learning çalışma alanı
 - **Proje türü**: machine learning framework. Bu durumda seçin **TensorFlow**
 - **Çözüme eklemek**: geçerli Visual Studio çözümünüzü veya bir oluşturma eklemek ve yeni bir çözüm açmak belirler
 - **Proje yolu**: kod kaydetmek için konum
 - **Proje adı**: türü **TensorFlowMNIST**
   

    ![Python uygulama şablonu kullanırken sonuç projesi](media\create-project\new-AzureSampleProject.png)

1. Visual Studio Proje dosyası oluşturur (bir `.pyproj` diskteki dosya) örnekte tanımlanan diğer dosyaların yanı sıra. "MNIST" şablonu ile proje pek çok dosya içeriyor.

    ![mnist](media\create-project\azml-mnist.png)

1. Azure Machine Learning projeye gönderin. 

    ![mnist](media\create-project\submit-azml.png)

1. Docker kapsayıcısı veya yerel makinenizde çalıştırma

    ![mnist](media\create-project\azml-local.png)
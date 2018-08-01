---
title: Azure Batch AI, modeli eğitmek için bir iş gönderdiniz
description: Train model bulut
keywords: yapay zeka, visual studio, modeli eğitme bulut
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.devlang: multiple
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- azure
ms.openlocfilehash: b9d66539d10fe97cefbba51295b43fcfa19be50a
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379838"
---
# <a name="train-ai-models-in-azure-batch-ai"></a>Azure Batch AI, yapay ZEKA modellerini eğitme

Batch AI, yapay ZEKA ve diğer makine öğrenimi modellerini Azure sanal makinelerini, GPU desteğine sahip VM'ler gibi kümelerinde eğitmek veri bilimcileri ve yapay ZEKA Araştırmacıları sağlayan yönetilen bir hizmettir. İşinizin gereksinimlerini tanımlamak, bulma girişleri ve çıkışları ve Batch AI depolamak nereye açıklarsınız. [Azure Batch AI hakkında daha fazla bilgi edinin](https://docs.microsoft.com/azure/batch-ai/overview)

Dinamik olarak Azure eğitimi modellerini ölçeği genişletebilirsiniz için yapay ZEKA için Visual Studio Araçları ile tümleşiktir.  Kaydederler [yapay ZEKA için Visual Studio Araçları yüklü](installation.md), Azure Machine Learning örnek galerideki önceden yapılmış tarifleri kullanarak yeni Python projesi oluşturmak daha kolaydır.

1. Visual Studio'yu başlatın. Açık **Sunucu Gezgini** açarak **yapay ZEKA Araçları** menü ve seçme **kümesi seçin**

    ![Küme Seçici](media\train-model\select-cluster.png)


2. Genişletin **yapay ZEKA Araçları**. Sahip olduğunuz herhangi bir Batch AI kaynağını otomatik olarak algılanır ve sunucu Gezgini'nde görünür.

    ![Örnek Galerisi](media\train-model\batchai.png)

3. Seçin **Görüntüle > Takım Gezgini...**  açmak için **Takım Gezgini** penceresi içinde GitHub veya Visual Studio Team Services bağlanabilir, ya da bir depoyu kopyalayın.

    ![Visual Studio Team Services, GitHub'ı gösteren ve bir depo kopyalama Takım Gezgini penceresi](media\train-model\team-explorer.png)

4. Altında alanına **yerel Git depoları**, girin `https://github.com/Microsoft/samples-for-ai`, kopyalanan dosyalar için bir klasör girin ve seçin **kopya**.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalar almak için belirli bir klasördür. Farklı `git clone` komutunu, Ekip Gezgini'nde bir kopya oluşturma otomatik olarak oluşturmaz bir alt klasör deponun adını.

5. Kopyalama tamamlandıktan sonra tıklayın **Dosya > çözüm Aç > Proje / çözüm**

    ![Örnek Galerisi](media\train-model\open-solution.png)

5. Açık **samples-for-ai\TensorFlowExamples\TensorFlowExamples.sln** dizinde kopyaladığınız depo

    ![Örnek Galerisi](media\train-model\tensorflowexamples.png)

5. Kümesi MNIST projesi olarak ** başlangıç projesi **

    ![Örnek Galerisi](media\train-model\mnist-startup.png)

1. ** Sağ tıklayın ** MNIST proje **işi Gönder**

    ![Örnek Galerisi](media\train-model\submit-job.png)

1. Seçin, **Azure Batch AI** küme'a tıklayın **alma**. Seçin `AzureBatchAI_TF_MNIST.json` hızlı bir şekilde kullanmak için hangi Docker görüntüsü gibi bazı varsayılan değerler doldurmak için dosya. Ardından **Gönder**

    ![Örnek Galerisi](media\train-model\submit-batch.png)
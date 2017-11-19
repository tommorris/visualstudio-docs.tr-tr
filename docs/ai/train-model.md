---
title: "Azure Batch AI modeli eğitmek için bir iş Sumbit"
description: Train model bulut
keywords: AI, visual studio, train model bulut
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: how-to article
ms.technology: visual studio
ms.devlang: multiple
ms.service: multiple
ms.openlocfilehash: d8289a482bc83741a6b6bf31499925f5d24d0192
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="train-ai-models-in-azure-batch-ai"></a>Azure Batch AI AI modelleri eğitme

Toplu AI veri bilimcileri ve AI araştırmacılarının AI ve diğer machine learning modellerini Azure sanal makineler, sanal makineleri GPU desteği de dahil olmak üzere, kümeleri üzerinde eğitmek sağlayan yönetilen bir hizmettir. İşinizin gereksinimlerini tanımlamak, rest girişleri bulmak ve çıktıları ve toplu AI depolamak nereye işler. [Azure Batch AI hakkında daha fazla bilgi edinin](https://docs.microsoft.com/azure/batch-ai/overview) 

Azure eğitim modellerinde çıkışı dinamik olarak ölçeklendirmek için AI için Visual Studio Araçları ile tümleşiktir.  Seçtiğiniz sonra [AI için Visual Studio Araçları yüklü](installation.md), Azure Machine Learning örnek Galerisi'nde önceden yapılmış tarif kullanarak yeni bir Python proje oluşturmak kolaydır.

1. Visual Studio'yu başlatın. Açık **Sunucu Gezgini** açarak **AI Araçları** menü ve seçme **küme seçin**  

    ![Küme Seçici](media\train-model\select-cluster.png)

     
2. Genişletme **AI Araçları**. Sahip olduğunuz toplu AI kaynakları otomatik olarak algılanır ve Sunucu Gezgini'nde görüntülenir. 
    
    ![Örnek Galerisi](media\train-model\batchai.png)

3. Seçin **Görünüm > Takım Gezgini...**  açmak için **Takım Gezgini** , GitHub veya Visual Studio Team Services bağlanmak veya için bir depoyu kopyalayın penceresi.

    ![Takım Gezgini penceresi gösteren Visual Studio Team Services, GitHub ve depo kopyalama](media\train-model\team-explorer.png)

4. Altında URL'si alanına **yerel Git depoları**, girin `https://github.com/Microsoft/samples-for-ai`, kopyalanan dosyalar için bir klasör girin ve seçin **kopya**.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalarını almak için belirli bir klasördür. Farklı `git clone` komutunu Takım Gezgini'nde kopyasını oluşturma otomatik olarak oluşturmaz alt depo adını.

5. Kopyalama tamamlandıktan sonra tıklatın **Dosya > çözümü Aç > Proje / çözüm**
    
    ![Örnek Galerisi](media\train-model\open-solution.png)

5. Açık **samples-for-ai\TensorFlowExamples\TensorFlowExamples.sln** dizinde depo kopyalanamıyor 

    ![Örnek Galerisi](media\train-model\tensorflowexamples.png)

5. Set MNIST projesi olarak ** başlangıç projesi **

    ![Örnek Galerisi](media\train-model\mnist-startup.png)

1. ** Sağ ** MNIST proje **işi Gönder**

    ![Örnek Galerisi](media\train-model\submit-job.png)

1. Seçin, **Azure Batch AI** küme ve ardından **alma**. Seçin `AzureBatchAI_TF_MNIST.json` hızlı bir şekilde kullanmak için hangi Docker görüntü gibi bazı varsayılan değerleri doldurmak için dosya. Ardından **Gönder**

    ![Örnek Galerisi](media\train-model\submit-batch.png)
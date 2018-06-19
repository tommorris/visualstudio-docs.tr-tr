---
title: Bulutta TensorFlow modeli Çalıştır
description: azure vm öğrenme derin tensorflow modeli Çalıştır
keywords: AI, visual studio, sanal makine öğrenme derin
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: tutorial
ms.devlang: python
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- multiple
ms.openlocfilehash: 7006802f38076283221b9351ba9660448e64a696
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
ms.locfileid: "30306727"
---
# <a name="train-a-tensorflow-model-in-the-cloud"></a>Bulutta TensorFlow modeli eğitmek

Bu öğreticide, bir TensorFlow modelini kullanarak biz eğitmek [MNIST dataset](http://yann.lecun.com/exdb/mnist/) bir Azure üzerinde [derin öğrenme](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/deep-learning-dsvm-overview) sanal makine.

MNIST veritabanı 60.000 örnekler Eğitim kümesi ve el yazısı basamak 10.000 örnekleri test kümesi vardır.

## <a name="prerequisites"></a>Önkoşullar
Başlamadan önce aşağıdaki yüklenmiş ve yapılandırılmış olduğundan emin olun:

### <a name="setup-azure-deep-learning-virtual-machine"></a>Sanal makine öğrenme Azure derin Kurulumu

> [!NOTE]
> Ayarlama **işletim sistemi türü** Linux için.

Derin öğrenme sanal makine ayarlıyor yönergeler bulunabilir [burada](https://docs.microsoft.com/azure/machine-learning/data-science-virtual-machine/provision-deep-learning-dsvm).

### <a name="remove-comment-in-parens"></a>Kaldır açıklamada parens

```bash
echo -e ". /etc/profile\n$(cat ~/.bashrc)" > ~/.bashrc
```

### <a name="download-sample-code"></a>Örnek kodu indirin

Bu karşıdan [GitHub deposunu](https://github.com/Microsoft/samples-for-ai) TensorFlow, CNTK, Theano ve daha derin öğrenme ile çalışmaya başlama örnekleri içeren.

## <a name="open-project"></a>Proje Aç

- Visual Studio'yu başlatın ve seçin **Dosya > Aç > Proje/çözüm**.

- Seçin **Tensorflow örnekler** indirildi ve açık örnekleri depo klasöründen **TensorflowExamples.sln** dosya.

![Proje Aç](media\tensorflow-local\open-project.png)

![Çözümü Aç](media\tensorflow-local\open-solution.png)

## <a name="add-azure-remote-vm"></a>Azure uzak VM ekleme

Sunucu Gezgini'nde, sağ tıklatın **uzak makineleri** düğümü seçin ve AI araçları düğümü altında "Ekle...". Uzak makine görünen adı, IP ana bilgisayar, SSH bağlantı noktası, kullanıcı adı ve parola/anahtar dosyası girin.

![Yeni bir uzak makine Ekle](media\tensorflow-vm\add-remote-vm.png)

## <a name="submit-job-to-azure-vm"></a>Azure VM işi gönderin
MNIST projeye sağ tıklayın **Çözüm Gezgini** seçip **işi Gönder**.

![Bir uzak makineye iş gönderme](media\tensorflow-vm\job-submission.png)

Gönderme penceresinde:

- Listesinde **kullanmak için küme**, Uzak makinenin seçin (ile "rm:" önekini) işi göndermek için.

- Girin bir **iş adı**.

- Tıklatın **gönderme**.

## <a name="check-status-of-job"></a>İş durumunu denetleme
Durum ve işlerinin ayrıntılarını görmek için: işe içinde gönderdiğiniz sanal makine genişletmek **Sunucu Gezgini**. Çift **işleri**.

![İş tarayıcı](media\tensorflow-vm\job-browser.png)

## <a name="clean-up-resources"></a>Kaynakları temizleme

Yakın gelecekte kullanmayı planlıyorsanız ve VM'yi durdurun. Bu öğreticiyi tamamladığınızda, kaynakları temizlemek için aşağıdaki komutu çalıştırın:

```azurecli-interactive
az group delete --name myResourceGroup
```

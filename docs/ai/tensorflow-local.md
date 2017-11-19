---
title: "Yerel olarak tensorflow modeli eğitmek"
description: "Tensorflow modeli AI araçları Visual Studio için yerel olarak çalıştırın."
keywords: AI, visual studio, tensorflow, yerel
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: quickstart
ms.technology: visual studio
ms.devlang: python
ms.service: multiple
ms.openlocfilehash: 2b48acc8cfea97a89c32ce7180d693246ca6ab26
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="train-a-tensorflow-model-locally"></a>Yerel olarak TensorFlow modeli eğitmek 

Bu hızlı başlangıç biz ile TensorFlow modeli eğitmek [MNIST](http://yann.lecun.com/exdb/mnist/) AI için Visual Studio Araçları yerel olarak veri kümesi. MNIST veritabanı 60.000 örnekler Eğitim kümesi ve el yazısı basamak 10.000 örnekleri test kümesi vardır. 

## <a name="prerequisites"></a>Önkoşullar

Başlamadan önce aşağıdakilerin yüklü olduğundan emin olun:

### <a name="google-tensorflow"></a>Google TensorFlow 

Bir terminal aşağıdaki komutu çalıştırın. 
```cmd
C:\>pip.exe install tensorflow
```

### <a name="numpy-and-scipy"></a>NumPy ve SciPy 
Yükleme [NumPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy) ve [SciPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy). 

### <a name="download-sample-code"></a>Örnek kodu indirin
Bu karşıdan [GitHub deposunu](https://github.com/Microsoft/samples-for-ai) TensorFlow, CNTK, Theano ve daha fazlasını arasında derin öğrenmeye Başlarken örnekleri içeren. 

## <a name="open-solution-and-train-model"></a>Modeli eğitmek ve çözümü açın

- Visual Studio'yu başlatın ve seçin **Dosya > Aç > Proje/çözüm**.

- Seçin **Tensorflow örnekler** indirildi ve açık örnekleri depo klasöründen **TensorflowExamples.sln** dosya. 

![Proje Aç](media\tensorflow-local\open-project.png)

![Çözümü Aç](media\tensorflow-local\open-solution.png)

- MNIST projede bulma **Çözüm Gezgini**seçin ve sağ tıklatıp **başlangıç projesi olarak ayarla**.

- **Başlat**'a tıklayın. 

- Çıktı konsolda yazdırılır.

![Örnek konsol çıktısı](media\tensorflow-local\console-output.png)

> [!div class="nextstepaction"]
> [Bulutta TensorFlow modeli eğitmek](tensorflow-vm.md)
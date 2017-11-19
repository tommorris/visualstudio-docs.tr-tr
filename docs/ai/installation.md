---
title: "Visual Studio için AI araçlarını yükleme"
description: "Visual Studio için AI araçları yükleme"
keywords: AI, visual studio
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: article
ms.technology: visual studio
ms.devlang: multiple
ms.service: multiple
ms.openlocfilehash: fba1b4d02c8b9bb26f315361c07aa3e7cfc530cf
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="installation"></a>Yükleme

AI için Visual Studio Araçları, Windows 64-bit işletim sistemlerinde yüklenebilir.

## <a name="installing-visual-studio-tools-for-ai"></a>AI için Visual Studio araçlarını yükleme

Bu uzantı çalışır [Visual Studio](https://docs.microsoft.com/visualstudio/) 2015, 2017, Community sürümü veya daha yüksek. 

Yüklemek için indirin [Visual Studio Market'te](http://aka.ms/vstoolsforai) veya Visual Studio içinde 

1. **Araçlar**> **Uzantılar ve güncelleştirmeler** 

![Windows CUDA yükleyin](media\installation\extensions.png)

1. **Arama** "Araçları için AI" için sağ üst köşedeki
2. Seçin **AI için Visual Studio Araçları**
3. Tıklatın **indirin**


## <a name="preparing-your-local-machine"></a>Yerel makine hazırlanıyor

Eğitim emin olmanız gerekir, yerel bilgisayarınızda modelleri öğrenme derin önce yüklü en son geçerli önkoşul yoktur. Bu, en son emin içerir sürücülerini ve kitaplıklarını NVIDIA (varsa) GPU için. Python ve Python yüklü de emin olmalısınız NumPy, SciPy ve Microsoft Bilişsel Araç Seti (CNTK), TensorFlow, Caffe2, MXNet, Keras, Theano, PyTorch ve/veya kullanmayı planlıyorsanız bağlayıcı gibi çerçeveleri öğrenme uygun derin gibi kitaplıkları Projenizde.

> [!NOTE]
>
> Aşağıdaki alt bölümlerde yazılım girişte kendi giriş sayfaları alınmıştır.

### <a name="nvidia-gpu-driver"></a>NVIDIA GPU sürücüsünün

Derin öğrenme çerçeveleri NVIDIA doğruluk bir hızda öğrenin ve doğru yapay zeka doğru ölçeklendirme makineleri olanak GPU yararlanın. Bilgisayarınızda NVIDIA GPU kartlarına varsa, lütfen ziyaret [burada](http://www.nvidia.com/Download/index.aspx) veya en son sürücü yüklemek için işletim sistemi güncelleştirmeyi deneyin.

### <a name="cuda"></a>CUDA

[CUDA](https://developer.nvidia.com/cuda-zone) olan paralel platform bilgi işlem ve programlama modeli tarafından NVIDIA geliştirmiştir.
GPU gücünü gücünden tarafından performans bilgi işlem çarpıcı artar sağlar.
Şu anda CUDA Araç Seti 8.0 derin öğrenme çerçeveleri tarafından gereklidir.

CUDA yüklemek için

- Bu ziyaret [site](https://developer.nvidia.com/cuda-80-ga2-download-archive)CUDA indirin ve yükleyin.
- CUDA çalışma zamanı kitaplıkları yüklediğinizden emin olun ve ardından CUDA ikili yolu % PATH % veya $Path ortam değişkenine ekleyin.
- Windows, bu yol "C:\Program Files\NVIDIA GPU bilgi işlem Toolkit\CUDA\v8.0\bin" varsayılan olarak açıktır.

![Windows CUDA yükleyin](media\installation\install_cuda_win.png)

### <a name="cudnn"></a>cuDNN

[cuDNN](https://developer.nvidia.com/cudnn) (CUDA derin sinir ağı kitaplık) NVIDIA tarafından derin sinir ağları için elemanlar GPU hızlandırılmış bir kitaplık değil. cuDNN v6 son derin öğrenme çerçeveleri tarafından gereklidir.

CuDNN yüklemek için
- Ziyaret [burada](https://developer.nvidia.com/rdp/cudnn-download) indirin ve en son paketini yükleyin.
- % PATH % veya $Path ortam değişkenine ikili cuDNN içeren dizini eklemek için emin olun.
- Windows üzerinde "C:\Program Files\NVIDIA GPU bilgi işlem Toolkit\CUDA\v8.0\bin için" cudnn64_6.dll kopyalayabilirsiniz.

> [!NOTE]
>
> Önceki derin öğrenme çerçeveler CNTK 2.0 ve TensorFlow 1.2.1 gibi cuDNN v5.1 gerekir.
> Ancak, birden çok cuDNN sürümü birlikte yükleyebilirsiniz.


### <a name="python"></a>Python

Python derin öğrenme uygulamalar için birincil programlama dili olmuştur.
**64-bit** Python dağıtım gereklidir ve [Python 3.5.4](https://www.python.org/downloads/release/python-354/) en iyi uyumluluk için önerilir.

### <a name="to-install-python-on-windows"></a>Windows üzerinde Python yüklemek için
- Biz yalnızca kendiniz için Python Başlatıcısı'nı yükleme önermek ve Python % PATH % ortam değişkenine ekleyin.
- Yüklemek ve Python içinde yazılmış yazılım paketlerini yönetmek için paket yönetim sistemi PIP yüklemek için emin olun.

Derin öğrenme çerçeveleri PIP kendi yüklemesi için kullanır.

![Windows üzerinde Python yüklemek](media\installation\install_python_win.png)

Sonra Python 3.5 doğru yüklenip yüklenmediğini doğrulamak ve bir terminal aşağıdaki komutları yürüterek PIP en son sürüme yükseltmek ihtiyacımız var:

- **Windows**
    ```cmd
    C:\Users\test>python -V
    Python 3.5.4

    C:\Users\test>pip3.5 -V
    pip 9.0.1 from c:\users\test\appdata\local\programs\python\python35\lib\site-packages (python 3.5)

    C:\Users\test>python -m pip install -U pip
    ```

- **macOS**
    ```bash
    MyMac:~ test$ python3.5 -V
    Python 3.5.4

    MyMac:~ test$ pip3.5 -V
    pip 9.0.1 from /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (python 3.5)

    MyMac:~ test$ python3.5 -m pip install -U pip
    ```

### <a name="python-on-visual-studio"></a>Visual Studio üzerinde Python

Python, Uzantılar ile Visual Studio'da tam olarak desteklenir.
Yükleme hakkında daha fazla bilgi [Python için Visual Studio Araçları](https://docs.microsoft.com/visualstudio/python/installation) daha fazla ayrıntı için.

### <a name="numpy-and-scipy"></a>NumPy ve SciPy

- **NumPy** küçük çok boyutlu diziler için çok fazla hızı ödün vermeden rasgele kayıtların büyük çok boyutlu diziler verimli bir şekilde yönetmek üzere tasarlanmış genel amaçlı bir dizi işleme paketidir.

- **SciPy** ("Sigh pasta" denilir) matematik, Bilim ve mühendislik, NumPy bağlı olarak açık kaynaklı bir yazılımdır.
1.0.0 sürümünden başlayarak, SciPy artık resmi önceden oluşturulmuş Tekerlek paketi için Windows olarak sahiptir.

NumPy ve SciPy yüklemek için bir terminal aşağıdaki komutu çalıştırın:
```bash
pip3.5 install -U numpy scipy
```

> [!NOTE]
>
> Varolan eski ya da resmi olmayan yukarıdaki komut yükseltmeleri (örn. üçüncü taraf paketlerden Windows için http://www.lfd.uci.edu/~gohlke/pythonlibs/) NumPy ve en son resmi olanlara SciPy.

### <a name="microsoft-cognitive-toolkit-cntk"></a>Microsoft Bilişsel Araç Seti (CNTK)

[Microsoft Bilişsel Araç Seti](https://cntk.ai) hesaplama adımları yönlendirilmiş grafik aracılığıyla bir dizi olarak sinir ağları açıklar birleşik bir derin öğrenme araç takımıdır. Python ve programlama dilleri BrainScript CNTK destekler.

> [!NOTE]
>
> CNTK macOS şu anda desteklemiyor.

CNTK Python paketini yüklemek için bkz: [CNTK yükleme](https://docs.microsoft.com/cognitive-toolkit/Setup-CNTK-on-your-machine)

### <a name="tensorflow"></a>TensorFlow

[TensorFlow](https://www.tensorflow.org/) veri akışı grafikleri kullanma sayısal hesaplama için bir açık kaynak yazılım kitaplığı.
Başvurmak [burada](https://www.tensorflow.org/install/) için ayrıntılı yükleme.

> [!NOTE]
>
> Sürüm 1.2 sürümünden itibaren TensorFlow macOS için artık GPU desteği sağlar.

### <a name="caffe2"></a>Caffe2

[Caffe2](https://caffe2.ai/) hafif, modüler ve ölçeklenebilir derin öğrenme çerçevedir.
Özgün Caffe üzerinde oluşturma, Caffe2 ifadesi, hızlı ve modülerlik aklınızda tasarlanmıştır.

Şu anda hiçbir önceden oluşturulmuş Caffe2 python Tekerlek paketi mevcut değil.

Ziyaret [burada](https://caffe2.ai/docs/getting-started.html) kaynak kodundan oluşturmak için.

### <a name="mxnet"></a>MXNet

[Apache (incubating) MXNet](https://mxnet.incubator.apache.org/) verimliliği ve esneklik için tasarlanmış bir derin öğrenme çerçevedir.
İmkan tanır **karışımı** [sembolik ve kesinlik temelli programlama](http://mxnet.io/architecture/index.html#deep-learning-system-design-concepts) verimliliğini ve üretkenliğini en üst düzeye çıkarmak için.

MXNet yüklemek için bir terminal aşağıdaki komutu çalıştırın:
- GPU ile
    ```bash
    pip3.5 install mxnet-cu80==0.12.0
    ```
- GPU
    ```bash
    pip3.5 install mxnet==0.12.0
    ```

### <a name="keras"></a>Keras

[Keras](https://keras.io/) Python ve çalışan yeteneğine CNTK, TensorFlow veya Theano üstte yazılmış bir üst düzey sinir ağları API'dır. Hızlı deneme etkinleştirme odak geliştirilmiştir. Mümkün olan en küçük gecikme ile sonuçlanması fikir gitme olanağı yapamamasına iyi araştırma yapmak için bir anahtardır.

Keras yüklemek için lütfen bir terminal aşağıdaki komutu çalıştırın:
```bash
pip3.5 install Keras==2.0.9
```

### <a name="theano"></a>Theano

[Theano](http://deeplearning.net/software/theano/) tanımlamak, en iyi duruma getirme ve çok boyutlu diziler verimli bir şekilde içeren matematiksel ifadeler değerlendirmek izin veren bir Python kitaplıktır.

Theano yüklemek için lütfen bir terminal aşağıdaki komutu çalıştırın:
```bash
pip3.5 install Theano==0.9.0
```

### <a name="pytorch"></a>PyTorch

[PyTorch](http://pytorch.org/) iki üst düzey özellikleri sağlayan bir python paket:
- Güçlü GPU hızlandırması ile tensor hesaplama (gibi numpy)
- Bir bant tabanlı autograd sisteminde yerleşik derin sinir ağları

PyTorch yüklemek için lütfen bir terminal aşağıdaki komutu çalıştırın:

- **Windows**
    - Henüz hiçbir resmi Tekerlek paketi yoktur. Üçüncü taraf indirebilirsiniz [Anaconda PyTorch paket](https://anaconda.org/peterjc123/pytorch/0.2.1/download/win-64/pytorch-0.2.1-py35h24644ff_0.2.1cu80.tar.bz2).
    - Giriş dizininize örneğin sıkıştırmasını "C:\Users\test\pytorch".
    - "C:\Users\test\pytorch\Lib\site-packages" % PYTHONPATH % ortam değişkenine ekleyin.

- **macOS**
    ```bash
    pip3.5 install http://download.pytorch.org/whl/torch-0.2.0.post3-cp35-cp35m-macosx_10_7_x86_64.whl
    ```
    > [!NOTE]
    >
    > macOS ikili dosyaları CUDA desteği yok, CUDA gerekirse kaynağından yükleyin

- **Linux**
    ```bash
    pip3.5 install http://download.pytorch.org/whl/cu80/torch-0.2.0.post3-cp35-cp35m-manylinux1_x86_64.whl
    ```
    > [!NOTE]
    >
    > Bu tek bir paket GPU ve CPU destekler.

Son olarak, Windows dışı üzerinde torchvision yükleyin:
```bash
pip3.5 install torchvision
```

### <a name="chainer"></a>Bağlayıcı

[Bağlayıcı](https://chainer.org/) sırasında esneklik amaçlayan bir Python tabanlı derin öğrenme çerçevedir.
Otomatik ayrım göre API'ler sağlar **tanımlamak tarafından-çalıştırma yaklaşım** (paketini dinamik hesaplama grafikleri) oluşturmak ve sinir ağları eğitmek için üst düzey API'leri nesne yönelimli yanı sıra.

CUDA desteğini etkinleştirmek için yükleme [CuPy](https://github.com/cupy/cupy):
```bash
pip3.5 install cupy
```

> [!NOTE]
>
> Windows üzerinde ihtiyacınız **2015** sürümü [Microsoft Visual Studio](https://www.visualstudio.com/) veya [Microsoft Visual C++ derleme Araçları](http://landinghub.visualstudio.com/visual-cpp-build-tools) CuPy CUDA 8.0 ile derlemek için.

Bağlayıcı yüklemek için lütfen bir terminal aşağıdaki komutu çalıştırın:
```bash
pip3.5 install chainer==3.0.0
```



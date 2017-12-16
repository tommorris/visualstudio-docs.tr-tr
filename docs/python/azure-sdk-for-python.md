---
title: "Python için Azure SDK | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: e7a31bf6bff3e7f53ee50283d8efbe2218b8e88f
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/13/2017
---
# <a name="azure-sdk-for-python"></a>Python için Azure SDK

Python için Azure SDK'sını kullanabilir ve Windows, Mac OSX ve Linux üzerinde çalışan uygulamalardan Microsoft Azure hizmetlerini yönetmek kolaylaştırır.

## <a name="installation"></a>Yükleme

Azure SDK'sını gelen yüklü [Python paket dizini](https://pypi.python.org/pypi/azure).

Yükleme **en yeni kararlı sürüm** (gibi destekler Python 2.7 ve 3.3 +):

```bash
pip install azure
```

Ayrıca izleyebilirsiniz [Python yüklemek ve SDK](https://azure.microsoft.com/documentation/articles/python-how-to-install/) Azure belgelerinde.

## <a name="documentation"></a>Belgeler

Belge üzerinde bulunabilir [python.readthedocs.org için azure sdk](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html).

[Python Geliştirici Merkezi için Azure SDK](http://azure.microsoft.com/develop/python/) öğreticileri sayısı gibi yararlı kaynaklara sayısı de vardır:

  - Web uygulamaları ile oluşturma [Django](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-flask-app), ve [Bottle](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
  - [BLOB Depolama](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-blob-storage)
  - [Tablo depolama](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-table-storage)
  - [Kuyruk depolama](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-queue-storage)
  - [DocumentDB](https://docs.microsoft.com/azure/documentdb/documentdb-python-application)
  - [Service Bus kuyrukları](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Hizmet veri yolu konuları/abonelikleri](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
  - [Hizmet Yönetimi](https://docs.microsoft.com/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Belgeler olmadan ortak API'ler için birim testleri içinde [SDK'ın GitHub deposunu](https://github.com/Azure/azure-sdk-for-python) iyi bilgi kaynağıdır:

- [Birim testleri](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Hizmet veri yolu birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Hizmet Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [Kaynak Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Destek

SDK'sı için Git deposu adresindedir [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python).

[Depo sorunları dosya](https://github.com/Azure/azure-sdk-for-python/issues) sorunları bulmak ya da SDK'ın kullanımıyla ilgili sorularınız varsa.

---
title: Python için Azure SDK
description: Python için Azure SDK'sı, Microsoft Azure hizmetlerinden herhangi bir platformda çalışan Python uygulamaları kullanmasını kolaylaştırır.
ms.date: 09/56/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 0a68027e975357a404cd7b4f29c837767c60e015
ms.sourcegitcommit: 95aedf723c6be5272c3c5a2911cb2bdec50e2148
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47228818"
---
# <a name="azure-sdk-for-python"></a>Python için Azure SDK

Python için Azure SDK'sını kullanma ve Windows, Mac OSX ve Linux'ta çalışan uygulamalar Microsoft Azure hizmetlerini yönetmenize daha kolay hale getirir.

## <a name="installation"></a>Yükleme

Azure SDK'ın yüklendiği [Python paket dizinini](https://pypi.python.org/pypi/azure).

Yükleme **en son kararlı sürüm** (Python 2.7 ve 3.x gibi destekler):

```command
pip install azure
```

De izleyebilirsiniz [yüklemeniz Python ve SDK'sı](https://docs.microsoft.com/azure/python-how-to-install/) Azure belgeleri.

## <a name="documentation"></a>Belgeler

Tüm belgeler bulundu [Azure Python Geliştirici Merkezi için](https://docs.microsoft.com/en-us/python/azure/?view=azure-python). Qucik deneyimi için bkz: [Python kullanarak bulut geliştirmeye başlayın](/python/azure/python-sdk-azure-get-started?view=azure-python).

Ayrıca bkz. Bu öğreticiler için diğer Azure Hizmetleri ile Python kullanarak:

- Azure uygulama hizmeti:
  - [Web uygulamaları oluşturma](/azure/app-service/containers/quickstart-python)
  - [Azure'da Docker Python ve PostgreSQL web uygulaması oluşturma](/azure/app-service/containers/tutorial-docker-python-postgresql-app)
- Azure Depolama:
  - [BLOB Depolama](/azure/storage/blobs/storage-quickstart-blobs-python)
  - [Tablo depolama ve Cosmos DB](/azure/cosmos-db/table-storage-how-to-use-python)
  - [Kuyruk depolama](/azure/storage/queues/storage-python-how-to-use-queue-storage)
  - [Flask ve Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- Hizmet veri yolu
  - [Service Bus kuyrukları](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Hizmet veri yolu konuları/abonelikleri](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Hizmet Yönetimi](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Belgeler olmadan ortak API'ler için birim testleri içindeki [SDK'sı GitHub deposu](https://github.com/Azure/azure-sdk-for-python) iyi bir bilgi kaynağı olan:

- [Birim testleri](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Service Bus birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Hizmet Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Destek

SDK'sı GitHub deposunu şu konumdadır [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Deponun sorunlar dosya](https://github.com/Azure/azure-sdk-for-python/issues) problemleri bulun ya da SDK'sının kullanım ile ilgili sorularınız varsa.

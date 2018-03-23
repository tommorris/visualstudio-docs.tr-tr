## <a name="create-a-kubernetes-development-environment-in-azure"></a>Kubernetes geliştirme ortamı oluşturma
Bağlı bir ortam tamamen Azure tarafından yönetilen ve geliştirme için optimize edilmiş Kubernetes tabanlı ortamları oluşturabilirsiniz. Komut adlı bir ortam oluşturur `mydevenvironment` içinde `eastus`.
```cmd
vsce env create --name mydevenvironment --location eastus
```

Desteklenen konumlar: `eastus`, `westeurope`

> [!Note]
> Bu komut, yaklaşık 6 dakika sürer. Bu kılavuz bekleme olmadan devam edebilirsiniz.

---
title: DisassemblyData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DisassemblyData
helpviewer_keywords:
- DisassemblyData structure
ms.assetid: 10e70aa7-9381-40d3-bdd1-d2cad78ef16c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0e97d2cc15e3b613fa56d2d4df1d5df8c68f9b06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="disassemblydata"></a>DisassemblyData
Görüntülenecek bir ayrıştırılmış yönerge tümleşik geliştirme ortamı (IDE) açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagDisassemblyData {   
   DISASSEMBLY_STREAM_FIELDS dwFields;  
   BSTR                      bstrAddress;  
   BSTR                      bstrAddressOffset;  
   BSTR                      bstrCodeBytes;  
   BSTR                      bstrOpcode;  
   BSTR                      bstrOperands;  
   BSTR                      bstrSymbol;  
   UINT64                    uCodeLocationId;  
   TEXT_POSITION             posBeg;  
   TEXT_POSITION             posEnd;  
   BSTR                      bstrDocumentUrl;  
   DWORD                     dwByteOffset;  
   DISASSEMBLY_FLAGS         dwFlags;  
} DisassemblyData;  
```  
  
```csharp  
public struct DisassemblyData {   
   public uint          dwFields;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrCodeBytes;  
   public string        bstrOpcode;  
   public string        bstrOperands;  
   public string        bstrSymbol;  
   public ulong         uCodeLocationId;  
   public TEXT_POSITION posBeg;  
   public TEXT_POSITION posEnd;  
   public string        bstrDocumentUrl;  
   public uint          dwByteOffset;  
   public uint          dwFlags;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `dwFields`  
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) hangi alanların doldurulmuş belirtir sabiti.  
  
 `bstrAddress`  
 Uzaklık bazı başlangıç noktası (genellikle ilişkili işlevi başlangıcı) olarak adresi.  
  
 `bstrCodeBytes`  
 Bu yönerge kodu bayt sayısı.  
  
 `bstrOpcode`  
 Bu yönerge için işlem kodu.  
  
 `bstrOperands`  
 Bu yönerge için işlenen.  
  
 `bstrSymbol`  
 Sembol adını varsa (ortak simgesi, etiket ve benzeri) adresiyle ilişkili.  
  
 `uCodeLocationId`  
 Bu kod konum tanımlayıcısı satır dağıtılamaz. Bir satır kod bağlam adresini başka bir kod bağlam adresinden daha büyükse, ardından ilk kodunda artık hata ayıklayabildiğinize konumu tanıtıcısı de ikinci kodu konumu tanımlayıcısını büyük.  
  
 `posBeg`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) bir belge ayrıştırılmış veri başladığı konumu karşılık gelir.  
  
 `posEnd`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) belgede ayrıştırılmış veri bittiği konumuna karşılık gelir.  
  
 `bstrDocumentUrl`  
 Dosya adları olarak temsil edilebilir metin belgeleri `bstrDocumentUrl` alan burada kaynak bulunabilir, dosya adı ile oturum doldurulmuş biçimini kullanarak `file://file name`.  
  
 Dosya adları olarak temsil edilemez metin belgeleri `bstrDocumentUrl` belge için benzersiz bir tanımlayıcıdır ve hata ayıklama altyapısı uygulamalıdır [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md) yöntemi.  
  
 Bu alan, ayrıca sağlama hakkında daha fazla bilgi içerebilir. Açıklamalar için bkz.  
  
 `dwByteOffset`  
 Kod satırı baştan yönerge olması bayt sayısı.  
  
 `dwFlags`  
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md) hangi bayrakların etkin belirtir sabiti.  
  
## <a name="remarks"></a>Açıklamalar  
 Her `DisassemblyData` yapısını ayrıştırılmış tek bir yönerge açıklar. Bu yapıları dizisi sunucudan döndürülen [okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) yöntemi.  
  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) yapısı, yalnızca metin tabanlı belgeler için kullanılır. Bu yönerge kaynak kodu aralığının bir deyim veya satır, örneğin oluşturulan yalnızca ilk yönergesi doldurulur, ne zaman `dwByteOffset == 0`.  
  
 Metinsel olmayan belgeler için belge bağlam koddan alınabilir ve `bstrDocumentUrl` alan boş bir değer olmalıdır. Varsa `bstrDocumentUrl` alandır aynı `bstrDocumentUrl` önceki alan `DisassemblyData` dizi öğesi, ardından ayarlayabilirsiniz `bstrDocumentUrl` null bir değere.  
  
 Varsa `dwFlags` alan sahip `DF_DOCUMENT_CHECKSUM` bayrağı ayarlanmışsa, ek sağlama toplamı bilgisi gösterdiği dize izleyen sonra `bstrDocumentUrl` alan. Özellikle, boş bir dize Sonlandırıcı sonra vardır, sırayla sağlama toplamı bayt sayısını gösteren bir 4 bayt değeri tarafından izlenir ve sağlama toplamı bayt tarafından sırayla izlenir sağlama toplamı algoritmasını tanımlayan bir GUID izler. Bu konudaki örnek kodlamak ve bu alanda kod çözme konusunda bkz [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
## <a name="example"></a>Örnek  
 `bstrDocumentUrl` Alan, bir dize dışında ek bilgiler içerebilir, varsa `DF_DOCUMENT_CHECKSUM` bayrağı ayarlanır. Oluşturma ve bu kodlu bir dize okuma işlemi basittir [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]. Bununla birlikte, [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)], başka bir konudur. Kişiler için merak, aşağıdaki örnek, kodlanmış dizesi oluşturmak için bir yol gösterir [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)] ve tek yönlü kodlu bir dize olarak çözecek [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
namespace MyNamespace  
    class MyClass  
    {  
        string EncodeData(string documentString,  
                          Guid checksumGuid,  
                          byte[] checksumData)  
        {  
            string returnString = documentString;  
  
            if (checksumGuid == null || checksumData == null)  
            {  
                // Nothing more to do. Just return the string.  
                return returnString;  
            }  
  
            returnString += '\0'; // separating null value  
  
            // Add checksum GUID to string.  
            byte[] guidDataArray  = checksumGuid.ToByteArray();  
            int    guidDataLength = guidDataArray.Length;  
            IntPtr pBuffer        = Marshal.AllocCoTaskMem(guidDataLength);  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, guidDataArray[i]);  
            }  
            // Copy guid data bytes to string as wide characters.  
            // Assumption: sizeof(char) == 2.  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum count (a 32-bit value).  
            Int32 checksumCount = checksumData.Length;  
            Marshal.StructureToPtr(checksumCount, pBuffer, true);  
            for (int i = 0; i < sizeof(Int32) / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum data.  
            pBuffer = Marshal.AllocCoTaskMem(checksumCount);  
            for (int i = 0; i < checksumCount; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, checksumData[i]);  
            }  
            for (int i = 0; i < checksumCount / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
            Marshal.FreeCoTaskMem(pBuffer);  
  
            return returnString;  
        }  
  
        void DecodeData(    string encodedString,  
                        out string documentString,  
                        out Guid   checksumGuid,  
                        out byte[] checksumData)  
       {  
           documentString = String.Empty;  
           checksumGuid = Guid.Empty;  
           checksumData = null;  
  
           IntPtr pBuffer = Marshal.StringToBSTR(encodedString);  
           if (null != pBuffer)  
           {  
               int bufferOffset = 0;  
  
               // Parse string out.  String is assumed to be Unicode.  
               documentString = Marshal.PtrToStringUni(pBuffer);  
               bufferOffset += (documentString.Length + 1) * sizeof(char);  
  
               // Parse Guid out.  
               // Read guid bytes from buffer and store in temporary  
               // buffer that contains only the guid bytes. Then the  
               // Marshal.PtrToStructure() can work properly.  
               byte[] guidDataArray  = checksumGuid.ToByteArray();  
               int    guidDataLength = guidDataArray.Length;  
               IntPtr pGuidBuffer    = Marshal.AllocCoTaskMem(guidDataLength);  
               for (int i = 0; i < guidDataLength; i++)  
               {  
                   Marshal.WriteByte(pGuidBuffer, i,  
                                     Marshal.ReadByte(pBuffer, bufferOffset + i);  
               }  
               bufferOffset += guidDataLength;  
               checksumGuid = (Guid)Marshal.PtrToStructure(pGuidBuffer, typeof(Guid));  
               Marshal.FreeCoTaskMem(pGuidBuffer);  
  
              // Parse out the number of checksum data bytes (always 32-bit value).  
              int dataCount = Marshal.ReadInt32(pBuffer, bufferOffset);  
              bufferOffset += sizeof(Int32);  
  
              // Parse out the checksum data.  
              checksumData = new byte[dataCount];  
              for (int i = 0; i < dataCount; i++)  
              {  
                  checksumData[i] = Marshal.ReadByte(pBuffer, bufferOffset + i);  
              }  
           }  
       }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [Okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)
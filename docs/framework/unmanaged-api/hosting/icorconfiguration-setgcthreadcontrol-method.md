---
title: Método ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762390"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>Método ICorConfiguration::SetGCThreadControl
Define a interface de retorno de chamada para o agendamento de threads para tarefas sem tempo de execução que, de outra forma, seriam bloqueadas para uma coleta de lixo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pGCThreadControl`  
 no Um ponteiro para um objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica o host sobre a suspensão de threads para tarefas sem tempo de execução.  
  
## <a name="remarks"></a>Comentários  
 O host pode escolher entre o retorno de chamada [IGCThreadControl:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) se deve reagendar um thread.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso em MSCorEE. dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Veja também

- [Interface ICorConfiguration](icorconfiguration-interface.md)

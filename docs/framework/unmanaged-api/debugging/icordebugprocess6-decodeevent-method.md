---
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 7c163311f9ce8f3d98ce72f45165a5e517c6c0aa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205509"
---
# <a name="icordebugprocess6decodeevent-method"></a>Método ICorDebugProcess6::DecodeEvent
Decodifica eventos de depuração gerenciados que foram encapsulados na carga de eventos de depuração de exceção nativo especialmente criado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pRecord`  
 [in] Um ponteiro para uma matriz de bytes de um evento de depuração de exceção nativo que inclui informações sobre um evento de depuração gerenciado.  
  
 `countBytes`  
 [in] O número de elementos nas matrizes de byte `pRecord`.  
  
 `format`  
 no Um membro de enumeração [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) que especifica o formato do evento de depuração não gerenciado.  
  
 `dwFlags`  
 [in] Um campo de bits que depende da arquitetura de destino e que especifica informações adicionais sobre o evento de depuração. Para sistemas Windows, ele pode ser membro da enumeração [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .  
  
 `dwThreadId`  
 [in] O identificador de sistema operacional do thread em que a exceção foi gerada.  
  
 `ppEvent`  
 fora Um ponteiro para o endereço de um objeto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) que representa um evento de depuração gerenciado decodificado.  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugProcess6](icordebugprocess6-interface.md)
- [Depurando interfaces](debugging-interfaces.md)

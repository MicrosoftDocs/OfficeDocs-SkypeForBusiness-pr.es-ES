---
title: Configurar el almacén de contactos personales en los equipos cliente de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal usado 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server.'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012903"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a>Configurar el almacén de contactos personales en los equipos cliente de Skype para Business Server
 
**Resumen:** Configurar el almacén de contactos personal usado 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server.
  
Si va a integrar Skype para Business Server y Exchange Server 2016 o Exchange Server 2013, debe configurar el almacén de contactos personal en los equipos de cliente que ejecutan Skype para la empresa. En concreto, debe configurar Skype para la empresa utilizar Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.
  
Tenga en cuenta que esto no es necesario en los equipos que ejecutan Skype para la empresa.
  
Para configurar este valor en un solo equipo, siga este procedimiento:
  
1. En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.
    
2. En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.
    
3. En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.
    
4. Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.
    
5. Tras crear el nuevo valor, escriba PersonalContactStoreOverride y presione ENTRAR para cambiar el nombre del valor.
    
6. Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.
    
Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener información detallada, vea la documentación de directiva de grupo en [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  


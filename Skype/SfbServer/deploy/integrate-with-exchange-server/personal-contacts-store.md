---
title: Configurar el almacén de contactos personales en los equipos cliente de Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: Configurar el almacén de contactos personal utilizado por los clientes heredados.'
ms.openlocfilehash: 5545f3c0f993b1974f59e90c0b6672f3ebd246e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894263"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar el almacén de contactos personales en los equipos cliente de Lync 2010
  
Si va a integrar Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, a continuación, debe configurar el almacén de contactos personal utilizado por los clientes. En concreto, debe configurar Skype para la empresa utilizar Exchange como el almacén de contactos personal y, al mismo tiempo, garantizar que los usuarios no puedan reemplazar esa decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.
  
> [!NOTE]
> El siguiente procedimiento sólo es necesario para los clientes mediante el cliente de Lync 2010 o una versión anterior. El cliente de Lync 2013 y todos los Skype para clientes empresariales no tendrán la opción de omitir la configuración de almacén de contactos.
  
Para configurar este valor en un solo equipo, siga este procedimiento:
  
1. En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.
2. En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.
3. En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.
4. Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.
5. Tras crear el nuevo valor, escriba PersonalContactStoreOverride y presione ENTRAR para cambiar el nombre del valor.
6. Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener información detallada sobre cómo hacer esto en 10 de Windows, vea el artículo [crear un objeto de directiva de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  

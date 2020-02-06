---
title: Configurar el almacén de contactos personales en equipos cliente de Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumen: configure el almacén de contactos personal usado por clientes heredados.'
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797031"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar el almacén de contactos personales en equipos cliente de Lync 2010
  
Si está integrando Skype empresarial Server 2015 y Exchange Server 2016 o Exchange Server 2013, debe configurar el almacén de contactos personales usado por los clientes. En particular, debe configurar Skype empresarial para usar Exchange como el almacén personal de contactos y, al mismo tiempo, asegurarse de que los usuarios no pueden reemplazar esta decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.
  
> [!NOTE]
> El siguiente procedimiento solo es necesario para los clientes que usan el cliente de Lync 2010 o una versión anterior. El cliente de Lync 2013 y todos los clientes de Skype empresarial no tendrán la opción de reemplazar la configuración del almacén de contactos.
  
Para configurar este valor en un solo equipo, siga este procedimiento:
  
1. En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.
2. En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.
3. En el Editor del Registro, expanda **HKEY_LOCAL_MACHINE**, **Software**, **Directivas**, **Microsoft** y, por último, **Communicator**.
4. Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.
5. Tras crear el nuevo valor, escriba PersonalContactStoreOverride y presione ENTRAR para cambiar el nombre del valor.
6. Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener más información sobre cómo hacerlo en Windows 10, consulte el artículo [crear un objeto de directiva de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  

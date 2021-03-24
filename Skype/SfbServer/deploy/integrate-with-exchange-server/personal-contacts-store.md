---
title: Configurar el almacén de contactos personales en equipos cliente de Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: configure el almacén de contactos personal que usan los clientes heredados.'
ms.openlocfilehash: 5f2131fd1e960e658d4257f0c86dd61a241aa499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109676"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar el almacén de contactos personales en equipos cliente de Lync 2010
  
Si integra Skype Empresarial Server 2015 y Exchange Server 2016 o Exchange Server 2013, debe configurar el almacén de contactos personal que usan los clientes. En concreto, debe configurar Skype Empresarial para que use Exchange como almacén de contactos personal y, al mismo tiempo, asegurarse de que los usuarios no puedan invalidar esa decisión. Para ello, cree y configure un valor del Registro en cada equipo cliente.
  
> [!NOTE]
> El siguiente procedimiento solo es necesario para los clientes que usan el cliente de Lync 2010 o versiones anteriores. El cliente de Lync 2013 y todos los clientes de Skype Empresarial no tendrán la opción de invalidar la configuración del almacén de contactos.
  
Para configurar este valor en un solo equipo, siga este procedimiento:
  
1. En el equipo cliente, haga clic **en Inicio** y, a continuación, en **Ejecutar**.
2. En el cuadro de diálogo **Ejecutar**, escriba regedit y, a continuación, presione ENTRAR.
3. En el Editor del Registro, **expanda HKEY_LOCAL_MACHINE**, **expanda Software**, expanda **Directivas**, **expanda Microsoft** y, a continuación, **expanda Communicator**.
4. Haga clic con **el Communicator**, elija **Nuevo** y, a continuación, haga clic en **DWORD (32 bits) Valor**.
5. Una vez creado el valor nuevo, escriba PersonalContactStoreOverride y pulse ENTRAR para cambiar el nombre del valor.
6. Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener más información sobre cómo hacerlo en Windows 10, consulta el artículo [Crear un objeto de directiva de](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) grupo.

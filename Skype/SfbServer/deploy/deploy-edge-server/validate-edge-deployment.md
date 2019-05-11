---
title: Validar la implementación perimetral en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores perimetrales está funcionando en Skype para Business Server.'
ms.openlocfilehash: e429b69a1c3470905027b35006de85d5a5711e31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893192"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar la implementación perimetral en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores perimetrales está funcionando en Skype para Business Server.
  
Una vez que haya implementado el servidor perimetral o grupo de servidores perimetrales, necesita saber si funciona correctamente. A continuación presentamos un par de cosas que pueden ayudar a con el entorno perimetral está conectado para confirmar a los servidores internos y los usuarios externos pueden conectarse a su Skype para entorno Business Server a través de su borde.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Comprobar la conectividad entre los servidores internos y los servidores perimetrales

Mientras se realiza la validación de conectividad automáticamente en el servidor perimetral o grupo de servidores perimetrales cuando se instalan los servidores perimetrales, puede confirmarlo aún usted mismo con Windows PowerShell. Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene la Administración Central de almacenar o cualquier equipo del dominio unidas en qué Skype para los componentes principales de servidor empresarial (OcsCore.msi) se instalan.
  
El resultado inicial de ejecutar este comando puede ofrecer un estado False, en lugar de True, para replicación. Si eso ocurre ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele algo de tiempo para completar la replicación y después ejecute el cmdlet Get-CsManagementStoreReplicationStatus de nuevo.
  
## <a name="verify-connectivity-for-your-external-users"></a>Comprobar la conectividad de usuarios externos

Hemos desarrollado una gran herramienta para confirmar la configuración del servidor perimetral y la capacidad de conectarse, enviar y recibir los mensajes correctos para los escenarios de servidor perimetral. Es el [sitio de Anaylzer de conectividad remota](https://testconnectivity.microsoft.com/). Se trata de un sitio que administra y mantiene el soporte técnico de Microsoft. Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario correcto para usted.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspectos que se deben tener en cuenta al probar la conectividad de los usuarios externos

Las pruebas para el acceso de usuarios externos tienen que incluir cada tipo de usuario interno que admite la organización, que podría incluir alguno de los elementos siguientes o todos ellos:
  
- Usuarios de al menos un dominio federado (le recomendamos probarlas todas).
    
- Usuarios anónimos.
    
- Usuarios de la organización que se registran en Skype para la empresa de forma remota, pero no se usen una VPN.
    
Estas pruebas determinará si el servidor perimetral es:
  
- Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.
    
  - Por ejemplo: telnet sip.contoso.com 443
    
  - Debe realizar las pruebas anteriores en los puertos que se está utilizando en el servidor perimetral o grupo de servidores perimetrales, dependiendo de la implementación.
    
- Logre una resolución de DNS externa precisa.
    
  - Desde fuera de la red, haga ping a cada uno de los FQDN externos de su servidor perimetral o grupo de servidores perimetrales. Incluso si se produce un error en el comando ping, verá las direcciones IP, que puede comparar las direcciones IP que haya asignado previamente.
    


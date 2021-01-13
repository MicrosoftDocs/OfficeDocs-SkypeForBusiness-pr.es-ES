---
title: Validar la implementación perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: obtenga información sobre cómo comprobar que la implementación del servidor perimetral o el grupo de servidores perimetrales funciona en Skype Empresarial Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804360"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar la implementación perimetral en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo comprobar que la implementación del servidor perimetral o del grupo de servidores perimetrales funciona en Skype Empresarial Server.
  
Una vez que haya implementado el servidor perimetral o el grupo de servidores perimetrales, debe saber si funciona correctamente. Estas son algunas de las cosas que pueden ayudar a confirmar que el entorno perimetral está conectado a los servidores internos y que los usuarios externos pueden conectarse a su entorno de Skype Empresarial Server a través de su servidor perimetral.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Comprobar la conectividad entre los servidores internos y los servidores perimetrales

Aunque la validación de conectividad se realiza automáticamente en el servidor perimetral o en el grupo de servidores perimetrales cuando se instalan los servidores perimetrales, puede confirmarlo usted mismo con Windows PowerShell. Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene el almacén de administración central o en cualquier equipo unido al dominio en el que estén instalados los componentes principales de Skype Empresarial Server (OcsCore.msi).
  
El resultado inicial de ejecutar este comando puede dar un estado False, en lugar de True, para la replicación. Si esto ocurre, ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele tiempo para completar la replicación y, a continuación, ejecute el cmdlet Get-CsManagementStoreReplicationStatus nuevo.
  
## <a name="verify-connectivity-for-your-external-users"></a>Comprobar la conectividad de los usuarios externos

Tenemos una excelente herramienta para confirmar la configuración del servidor perimetral y la capacidad de conectarse, enviar y recibir los mensajes correctos para escenarios de servidor perimetral. Es el sitio [Desatilizador de conectividad remota.](https://testconnectivity.microsoft.com/) Este es un sitio administrado y mantenido por el Soporte técnico de Microsoft. Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario adecuado.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspectos que se deben tener en cuenta al probar la conectividad de usuarios externos

Cualquier prueba para el acceso de usuarios externos debe incluir cada tipo de usuario interno compatible con la organización, que puede incluir cualquiera de los siguientes elementos o todos ellos:
  
- Usuarios de al menos un dominio federado (recomendamos probarlos todos).
    
- Usuarios anónimos.
    
- Usuarios de su organización que hayan iniciado sesión en Skype Empresarial de forma remota, pero que no estén usando VPN.
    
Estas pruebas determinarán si el servidor perimetral es:
  
- Escuchar en los puertos necesarios mediante un cliente telnet desde fuera de la red.
    
  - Por ejemplo: telnet sip.contoso.com 443
    
  - Debe realizar la prueba anterior en los puertos que use en el servidor perimetral o en el grupo de servidores perimetrales, en función de la implementación.
    
- Realizar una resolución dns externa precisa.
    
  - Desde fuera de la red, haga ping a cada uno de los FQDN externos de su servidor perimetral o grupo de servidores perimetrales. Incluso si se produce un error en el ping, verá las direcciones IP, que puede comparar las direcciones IP que asignó anteriormente.
    


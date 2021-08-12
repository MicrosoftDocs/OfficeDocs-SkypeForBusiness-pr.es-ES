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
ms.openlocfilehash: b2d44018bc43f8335081bcfc961108255240095031983066d54463dabc2538ee
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320932"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar la implementación perimetral en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo comprobar que la implementación del servidor perimetral o el grupo de servidores perimetrales funciona en Skype Empresarial Server.
  
Una vez que haya implementado el servidor perimetral o el grupo de servidores perimetrales, debe saber si funciona correctamente. Estos son algunos aspectos que pueden ayudar a confirmar que el entorno perimetral está conectado a los servidores internos y también que los usuarios externos pueden conectarse a su entorno Skype Empresarial Server a través de edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Comprobar la conectividad entre los servidores internos y los servidores perimetrales

Aunque la validación de la conectividad se realiza automáticamente en el servidor perimetral o el grupo de servidores perimetrales cuando se instalan los servidores perimetrales, puede confirmarlo usted mismo con Windows PowerShell. Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene el almacén de administración central o en cualquier equipo unido al dominio en el que Skype Empresarial Server componentes principales (OcsCore.msi) estén instalados.
  
El resultado inicial de ejecutar este comando puede dar un estado False, en lugar de True, para la replicación. Si esto sucede, ejecute el cmdlet Invoke-CsManagementStoreReplication. Déle algún tiempo para completar la replicación y, a continuación, vuelva a ejecutar Get-CsManagementStoreReplicationStatus cmdlet.
  
## <a name="verify-connectivity-for-your-external-users"></a>Comprobar la conectividad de los usuarios externos

Tenemos una excelente herramienta para confirmar la configuración del servidor perimetral y la capacidad de conectar, enviar y recibir los mensajes correctos para escenarios de servidor perimetral. Es el sitio [anaylzer de conectividad remota.](https://testconnectivity.microsoft.com/) Este es un sitio administrado y mantenido por el soporte técnico de Microsoft. Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario adecuado.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspectos a tener en cuenta al probar la conectividad de usuarios externos

Cualquier prueba para el acceso de usuarios externos debe incluir cada tipo de usuario interno compatible con su organización, lo que podría incluir cualquiera o todas las siguientes opciones:
  
- Los usuarios de al menos un dominio federado (recomendamos probarlos todos).
    
- Usuarios anónimos.
    
- Los usuarios de la organización que han iniciado sesión Skype Empresarial de forma remota, pero que no usan VPN.
    
Estas pruebas determinarán si el servidor perimetral es:
  
- Escuchar en los puertos necesarios mediante un cliente telnet desde fuera de la red.
    
  - Por ejemplo: telnet sip.contoso.com 443
    
  - Debe realizar la prueba anterior en los puertos que está usando en el servidor perimetral o el grupo de servidores perimetrales, según la implementación.
    
- Realizar una resolución de DNS externa precisa.
    
  - Desde fuera de la red, haga ping en cada uno de los FQDN externos del servidor perimetral o del grupo de servidores perimetrales. Incluso si se produce un error en el ping, verá las direcciones IP, que puede comparar las direcciones IP que asignó anteriormente.
    


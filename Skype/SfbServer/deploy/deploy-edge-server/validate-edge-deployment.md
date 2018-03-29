---
title: Validar la implementación perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumen: Conozca cómo comprobar que la implementación de servidor perimetral o grupo de servidores del servidor perimetral funciona en Skype para Business Server 2015.'
ms.openlocfilehash: 02f909310e6b491ae97e31b7013b1307c7688ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a>Validar la implementación perimetral en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo comprobar que la implementación de servidor perimetral o grupo de servidores del servidor perimetral funciona en Skype para Business Server 2015.
  
Una vez que haya implementado el servidor perimetral o un grupo de servidores de servidor perimetral, necesitará saber si funciona correctamente. Aquí hay un par de cosas que pueden ayudar a confirmar su entorno perimetral está conectado a los servidores internos y los usuarios externos pueden conectarse a su Skype para Business Server 2015 entorno a través de su borde.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Comprobar la conectividad entre los servidores internos y los servidores perimetrales

Mientras se realiza la validación de conectividad automáticamente en el servidor perimetral o grupo de servidores de borde cuando se instalan los servidores perimetrales, puede confirmarlo todavía usted mismo con Windows PowerShell. Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno que tiene la Administración Central de almacén o cualquier equipo unido dominio en qué Skype para componentes de núcleo de Business Server 2015 (OcsCore.msi) se instalan.
  
El resultado inicial de ejecutar este comando puede ofrecer un estado False, en lugar de True, para replicación. Si eso ocurre ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele algo de tiempo para completar la replicación y después ejecute el cmdlet Get-CsManagementStoreReplicationStatus de nuevo.
  
## <a name="verify-connectivity-for-your-external-users"></a>Comprobar la conectividad de usuarios externos

Tenemos una gran herramienta para confirmar la configuración del servidor de borde y la capacidad de conectar, enviar y recibir los mensajes correctos para escenarios de servidor perimetral. Es el [sitio de Anaylzer de conectividad remota](https://testconnectivity.microsoft.com/). Se trata de un sitio que administra y mantiene el soporte técnico de Microsoft. Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario correcto para usted.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspectos que se deben tener en cuenta al probar la conectividad de los usuarios externos

Las pruebas para el acceso de usuarios externos tienen que incluir cada tipo de usuario interno que admite la organización, que podría incluir alguno de los elementos siguientes o todos ellos:
  
- Usuarios de al menos un dominio federado (le recomendamos probarlas todas).
    
- Usuarios anónimos.
    
- Usuarios de la organización que se registran remotamente en Skype para el negocio, pero no mediante VPN.
    
Estas pruebas determinará si el servidor perimetral es:
  
- Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.
    
  - Por ejemplo: telnet sip.contoso.com 443
    
  - Debe realizar la prueba anterior en los puertos que se utiliza en el servidor perimetral o grupo de servidores de borde, dependiendo de su implementación.
    
- Logre una resolución de DNS externa precisa.
    
  - Desde fuera de la red, haga ping en cada uno de los FQDN externos del servidor perimetral o grupo de servidores de borde. Incluso si falla el comando ping, verá las direcciones IP, que puede comparar las direcciones IP que haya asignado previamente.
    


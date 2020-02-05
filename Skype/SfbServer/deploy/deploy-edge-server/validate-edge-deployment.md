---
title: Validar la implementación perimetral en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Aprenda a comprobar que su implementación del servidor perimetral o grupo de servidores perimetral funciona en Skype empresarial Server.'
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768303"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar la implementación perimetral en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo comprobar que su implementación del servidor perimetral o grupo de servidores perimetral funciona en Skype empresarial Server.
  
Una vez que haya implementado el servidor perimetral o el grupo de servidores perimetrales, tendrá que saber si funciona correctamente. Este es un par de cosas que pueden ayudarle a confirmar que su entorno perimetral está conectado a sus servidores internos y que sus usuarios externos pueden conectarse a su entorno de Skype empresarial Server a través de su borde.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Comprobar la conectividad entre los servidores internos y los servidores perimetrales

Aunque la validación de la conectividad se realiza automáticamente en el servidor perimetral o en el grupo de servidores perimetrales cuando los servidores perimetrales están instalados, aún puede confirmarlo por sí mismo con Windows PowerShell. Ejecute el cmdlet Get-CsManagementStoreReplicationStatus en el servidor interno, que tiene el almacén de administración central o cualquier equipo unido al dominio en el que estén instalados los componentes básicos de Skype empresarial Server (OcsCore. msi).
  
El resultado inicial de ejecutar este comando puede ofrecer un estado False, en lugar de True, para replicación. Si eso ocurre ejecute el cmdlet Invoke-CsManagementStoreReplication. Dele algo de tiempo para completar la replicación y después ejecute el cmdlet Get-CsManagementStoreReplicationStatus de nuevo.
  
## <a name="verify-connectivity-for-your-external-users"></a>Comprobar la conectividad de usuarios externos

Tenemos una excelente herramienta para confirmar la configuración del servidor perimetral, así como la capacidad de conectar, enviar y recibir los mensajes correctos para escenarios de servidor perimetral. Es el [sitio de Anaylzer de conectividad remota](https://testconnectivity.microsoft.com/). Se trata de un sitio que administra y mantiene el soporte técnico de Microsoft. Para usar esta herramienta, vaya al sitio web y siga las instrucciones para elegir el escenario correcto para usted.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Aspectos que se deben tener en cuenta al probar la conectividad de los usuarios externos

Las pruebas para el acceso de usuarios externos tienen que incluir cada tipo de usuario interno que admite la organización, que podría incluir alguno de los elementos siguientes o todos ellos:
  
- Usuarios de al menos un dominio federado (le recomendamos probarlas todas).
    
- Usuarios anónimos.
    
- Los usuarios de su organización que han iniciado sesión en Skype empresarial de forma remota, pero que no usan VPN.
    
Estas pruebas determinarán si su servidor perimetral es:
  
- Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.
    
  - Por ejemplo: telnet sip.contoso.com 443
    
  - Debe realizar la prueba anterior en los puertos que está usando en el servidor perimetral o en el grupo de servidores perimetrales, en función de la implementación.
    
- Logre una resolución de DNS externa precisa.
    
  - Desde fuera de la red, haga ping a cada uno de los FQDN externos de su servidor perimetral o al grupo de servidores perimetrales. Incluso si el ping falla, verá las direcciones IP, que puede comparar las direcciones IP que haya asignado previamente.
    


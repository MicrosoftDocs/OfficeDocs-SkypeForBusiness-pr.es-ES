---
title: Implementar la omisión de medios en Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lea este tema para obtener información sobre los pasos para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119369"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implementar la omisión de medios en Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

Lea este tema para obtener información sobre los pasos para implementar la omisión de medios con Cloud Connector Edition versión 2.0 y versiones posteriores. 
  
La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la Red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC) y eliminar el componente Cloud Connector Edition de la ruta de acceso multimedia. Vea también [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar el desvío de medios

Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio web de desvío de medios y activar la omisión de medios en la configuración del espacio empresarial. El servicio web de desvío de medios se implementa automáticamente en cada servidor de mediación. Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrido (sitio) y este nombre debe ser de un dominio SIP registrado para la voz híbrida. El nombre del servicio debe ser el mismo en todos los dispositivos de Cloud Connector y en todos los sitios RTC, independientemente de la ubicación del cliente. El servicio web solo debe estar disponible internamente en la red.
  
Un administrador de inquilinos debe configurar un registro DNS A en la producción interna de Active Directory. Si tiene un entorno complejo de varios sitios, vea el ejemplo de Ejemplo: registros DNS de sitios web de omisión de medios [en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example). El registro DNS solo debe resolverse para clientes de red internos; no debe resolverse para clientes de red externos.
  
Después de configurar DNS, conéctese a Skype Empresarial Online mediante PowerShell remoto con credenciales de administrador de Skype Empresarial. Para obtener más información, [vea Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
En la sesión de PowerShell, escriba los siguientes comandos para habilitar la omisión de medios:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Habilitar la omisión de medios es un proceso de dos pasos. El cmdlet New-CsNetworkMedia no guarda inmediatamente la nueva configuración; solo crea la configuración en la memoria. El objeto creado por este cmdlet debe guardarse en una variable y, a continuación, asignarse a la propiedad MediaBypassSettings de la configuración de red. Para obtener más información, vea [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda ejecutar los comandos necesarios antes de habilitar a los usuarios.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar la configuración de desvío de medios

Puede comprobar la configuración de desvío de medios de la siguiente manera. 
  
Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la replicación local, conéctese a los servidores de mediación de Cloud Connector, ejecute el siguiente comando en PowerShell y confirme que Enabled=True y AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la configuración del cliente, salga del cliente de Skype Empresarial, vuelva a iniciar sesión y confirme que el cliente ha recibido la dirección URL del servicio de la siguiente manera:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la definida.
    
## <a name="change-media-bypass-parameters"></a>Cambiar parámetros de omisión de medios

Los administradores de inquilinos pueden cambiar el nombre DNS del servicio web ejecutando el siguiente cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Los clientes deben cerrar sesión e iniciar sesión para obtener el nuevo nombre de servicio y reconocer el cambio. 
  
## <a name="temporarily-disable-media-bypass"></a>Deshabilitar temporalmente la omisión de medios

Este escenario puede ser útil para la solución de problemas o el mantenimiento. Para deshabilitar el servicio, ejecute los cmdlets siguientes:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Después de realizar el cambio, los cambios podrían tardar algún tiempo en replicarse en todos los conectores de nube. Para comprobar el estado de replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación de Cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Después de replicar los cambios, el servicio web del servidor de mediación empezará a rechazar las solicitudes de cliente para el servicio de omisión de medios.
  
## <a name="disable-media-bypass-permanently"></a>Deshabilitar la omisión de medios de forma permanente

Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrador también tendrá que quitar las direcciones web para la omisión de medios de los servidores DNS internos. Después de realizar el cambio, los cambios podrían tardar algún tiempo en replicarse en todos los dispositivos de Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Ejemplo: registros DNS de sitios web de desvío de medios en entornos complejos de varios sitios
<a name="Example"> </a>

Los clientes recibirán la dirección web del servicio web de desvío de medios desde un servidor DNS interno. El nombre del servicio web será el mismo en todos los dispositivos de Cloud Connector y en los sitios RTC de Cloud Connector. En un entorno complejo de varios sitios, se recomienda usar la directiva DNS de Windows 2016 para la administración de tráfico basada en Geo-Location, para que los clientes se puedan redirigir al servicio web que es local para su red. 
  
Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).
  
A continuación se muestra un ejemplo de configuración para una empresa con varios sitios que usan la directiva DNS de Windows 2016 para la administración Geo-Location de tráfico basado en aplicaciones.
  
El nombre del servicio de omisión es "hybridvoice.adatum.biz".
  
El sitio de Ámsterdam tiene cuatro dispositivos cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
El sitio de Seattle tiene tres dispositivos cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Con Geo-Location de tráfico basado en servidores, los servidores DNS se configurarían de la siguiente manera:
  
1. Cree subredes de cliente DNS para las subredes de Ámsterdam y Seattle.
    
2. Cree ámbitos de zona DNS para adatum.biz para Ámsterdam y Seattle.
    
3. Cree registros DNS en cada ámbito de zona DNS.
    
    Ámsterdam
    
   - Tipo A;
    
   - Nombre : hybridvoice en la zona ADATUM.BIZ DNS
    
   - Objetivo: 192.168.1.45
    
     Crear registros adicionales para servidores de mediación adicionales
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tipo A
    
   - Nombre : hybridvoice en adatum.biz zona DNS
    
   - Objetivo: 10.10.1.8
    
     Crear registros adicionales para servidores de mediación adicionales
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Cree la directiva DNS que conecte las subredes de cliente a los ámbitos de zona adecuados para garantizar la resolución de DNS deseada.
    
En este momento, los clientes que hacen consultas DNS desde la subred de Ámsterdam para hybridvoice.adatum.biz devolverán el 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que hacen el mismo formulario de consulta Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.10.

> [!NOTE]
> Si el dispositivo CCE no parece obtener la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto. Puede usar PowerShell remoto para comprobar el estado del dispositivo con Get-CsHybridPSTNAppliance o usar PowerShell en el host CCE para comprobar el estado con Get-CcApplianceStatus.

  
## <a name="see-also"></a>Ver también
<a name="Example"> </a>

[Plan para la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
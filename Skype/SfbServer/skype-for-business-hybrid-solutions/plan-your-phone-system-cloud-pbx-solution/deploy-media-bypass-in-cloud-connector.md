---
title: Implementación de la omisión de medios en Cloud Connector Edition
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
description: Lea este tema para obtener información sobre los pasos necesarios para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359316"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implementación de la omisión de medios en Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Lea este tema para obtener información sobre los pasos necesarios para implementar la omisión de medios con Cloud Connector Edition, versión 2,0 y posteriores. 
  
La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente de Cloud Connector Edition de la ruta de medios. Consulte también [Plan for Media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar el desvío de medios

Para habilitar la omisión de medios, debe configurar el nombre DNS del servicio Web de omisión de medios y activar la omisión de medios en la configuración del espacio empresarial. El servicio Web de omisión de medios se implementa automáticamente en cada servidor de mediación. Un administrador de inquilinos debe elegir un nombre para un servicio de voz híbrida (sitio) y este nombre debe pertenecer a un dominio SIP registrado para la voz híbrida. El nombre del servicio debe ser el mismo en todos los dispositivos de Cloud Connector y en todos los sitios RTC, independientemente de la ubicación del cliente. El servicio web solo debe estar disponible internamente en la red.
  
Un administrador de inquilinos debe configurar un registro A de DNS en el Active Directory de producción interna. Si tiene un entorno de varios sitios complejo, vea el ejemplo en el ejemplo [: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example). El registro DNS solo debe resolverse para los clientes de la red interna; no debe resolverse para los clientes de red externos.
  
Después de configurar DNS, conéctese a Skype empresarial online mediante PowerShell remoto con credenciales de administrador de Skype empresarial. Para obtener más información, consulte [configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
En la sesión de PowerShell, escriba los siguientes comandos para habilitar la omisión de medios:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

La habilitación de la omisión de medios es un proceso de dos pasos. El cmdlet New-CsNetworkMedia no guarda inmediatamente la nueva configuración; solo crea la configuración en la memoria. El objeto creado por este cmdlet se debe guardar en una variable y, a continuación, asignarse a la propiedad MediaBypassSettings de la configuración de red. Para obtener más información, consulte [ejemplo: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replicación entre los componentes locales y en línea puede tardar hasta 24 horas, por lo que Microsoft recomienda que ejecute los comandos necesarios antes de habilitar a los usuarios.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar la configuración de omisión de medios

Puede comprobar la configuración de la omisión de medios de la siguiente manera. 
  
Para comprobar la replicación en línea en el grupo de inquilinos, ejecute el siguiente comando en el PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la replicación local, conéctese a los servidores de mediación de Cloud Connector, ejecute el siguiente comando en PowerShell y confirme que Enabled = true y AlwaysBypass = true
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Para comprobar la configuración del cliente, cierre la sesión del cliente de Skype empresarial, vuelva a iniciar sesión y confirme que el cliente haya recibido la dirección URL del servicio de la siguiente manera:
  
1. Abrir%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Busque hybridconfigserviceinternalurl y confirme que la dirección URL coincida con la que ha definido.
    
## <a name="change-media-bypass-parameters"></a>Cambiar los parámetros de omisión de medios

Los administradores de espacios empresariales pueden cambiar el nombre DNS del servicio Web mediante la ejecución del siguiente cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Los clientes tienen que cerrar sesión e iniciar sesión para obtener el nuevo nombre del servicio y reconocer el cambio. 
  
## <a name="temporarily-disable-media-bypass"></a>Deshabilitar temporalmente el desvío de medios

Este escenario puede ser útil para solucionar problemas o realizar el mantenimiento. Para deshabilitar el servicio, ejecute los cmdlets siguientes:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Tras realizar el cambio, los cambios podrían tardar algún tiempo en replicarse a todos los conectores en la nube. Para comprobar el estado de la replicación, ejecute el siguiente cmdlet en PowerShell en los servidores de mediación de Cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Una vez que se replican los cambios, el servicio Web en el servidor de mediación iniciará el rechazo de solicitudes de cliente para el servicio de omisión de medios.
  
## <a name="disable-media-bypass-permanently"></a>Deshabilitar la omisión de medios de forma permanente

Para deshabilitar permanentemente la omisión de medios, un administrador de inquilinos debe ejecutar los siguientes comandos: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un administrador también tendrá que quitar las direcciones web de la omisión de medios de los servidores DNS internos. Tras realizar el cambio, los cambios podrían tardar algún tiempo en replicarse a todos los dispositivos de Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Ejemplo: registros DNS del sitio web de omisión de medios en entornos complejos de varios sitios
<a name="Example"> </a>

Los clientes recibirán la dirección web del servicio Web de omisión de medios de un servidor DNS interno. El nombre del servicio Web será el mismo en todos los equipos de Cloud Connector y los sitios RTC de Cloud Connector. En un entorno complejo con varios sitios, se recomienda usar la Directiva DNS de Windows 2016 para la administración de tráfico basada en la ubicación geográfica, de modo que los clientes se puedan redirigir al servicio Web local de su red. 
  
Para obtener más información sobre las directivas DNS de Windows 2016, consulte [usar la Directiva DNS para la administración geográfica del tráfico basado en servidores principales](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
El siguiente es un ejemplo de configuración para una empresa con varios sitios que usan la Directiva DNS de Windows 2016 para la administración de tráfico basada en la ubicación geográfica.
  
El nombre del servicio de omisión es "hybridvoice.adatum.biz".
  
El sitio de Amsterdam tiene cuatro dispositivos de Cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
El sitio de Seattle tiene tres dispositivos de Cloud Connector implementados con las siguientes direcciones IP del servidor de mediación:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Mediante la administración geográfica del tráfico basada en la ubicación geográfica, los servidores DNS se configurarían de la siguiente manera:
  
1. Cree subredes de cliente DNS para las subredes de Amsterdam y Seattle.
    
2. Cree ámbitos de zona DNS para adatum.biz tanto para Ámsterdam como para Seattle.
    
3. Crear registros DNS en cada ámbito de zona DNS.
    
    Ámsterdam
    
   - Escriba A;
    
   - Nombre: hybridvoice en la zona DNS adatum.biz
    
   - Destino: 192.168.1.45
    
     Crear registros adicionales para otros servidores de mediación
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Quito
    
   - Escriba un
    
   - Nombre: hybridvoice en la zona DNS adatum.biz
    
   - Destino: 10.10.1.8
    
     Crear registros adicionales para otros servidores de mediación
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Cree la Directiva DNS que conecta las subredes del cliente con los ámbitos de zona apropiados para garantizar la resolución DNS deseada.
    
En este momento, los clientes que realizan consultas DNS desde la subred de Amsterdam para hybridvoice.adatum.biz devolverán las direcciones 192.168.1.45, 192.168.1.46, 192.168.1.47 y 192.168.1.48, mientras que los clientes que tengan el mismo formato de consulta Seattle devolverán 10.10.1.8, 10.10.1.9 y 10.10.1.10.

> [!NOTE]
> Si el dispositivo CCE no parece que esté recibiendo la configuración actualizada, compruebe si el dispositivo puede ponerse en contacto con el inquilino a través de PowerShell remoto. Puede usar PowerShell remoto para comprobar el estado del dispositivo con get-CsHybridPSTNAppliance o usar PowerShell en el host CCE para comprobar el estado con get-CcApplianceStatus.

  
## <a name="see-also"></a>Recursos adicionales
<a name="Example"> </a>

[Plan para la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

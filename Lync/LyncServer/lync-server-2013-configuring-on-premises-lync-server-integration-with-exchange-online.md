---
title: "Lync Server 2013: Config. de integración local de Lync Server con Exchange Online"
TOCTitle: Configuración de la integración local de Lync Server 2013 con Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48276065
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la integración local de Lync Server 2013 con Exchange Online

 

_**Última modificación del tema:** 2014-07-02_

Los clientes que usan implementaciones locales de Lync Server 2013 pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el Servidor perimetral en su implementación local de Lync Server realizando las siguientes tareas:

  - Configurar un espacio de direcciones SIP compartido

  - Configurar un proveedor de hospedaje en el Servidor perimetral

  - Comprobar la replicación de la Almacén de administración central actualizada

## Configurar un espacio de direcciones SIP compartido

Para la integración local de Lync Server 2013 con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El espacio de direcciones del dominio SIP es compatible con Lync Server y con el servicio de Exchange Online.

Mediante el Shell de administración de Lync Server, configure el Servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration** mediante los parámetros mostrados en el ejemplo siguiente:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en un escenario de espacio de direcciones SIP compartido con Lync Server y Exchange Online.

Para obtener más información sobre el uso del Shell de administración de Lync Server, vea [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Configurar un proveedor de hospedaje en el servidor perimetral

Mediante el Shell de administración de Lync Server, configure un proveedor de hospedaje en el Servidor perimetral ejecutando el cmdlet **New-CsHostingProvider**, mediante los parámetros del ejemplo siguiente:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification


> [!NOTE]
> Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro <STRONG>ProxyFqdn</STRONG> de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".



  - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, “Exchange Online). Los valores que contienen espacios deben aparecer en comillas dobles.

  - **Enabled** indica si la conexión de red entre su dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.

  - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Este parámetro debe estar configurado en True.

  - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Lync Server. Este parámetro debe estar configurado en False.

  - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

  - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje se incluye en su topología de Lync Server. Este parámetro debe estar configurado en False.

  - **VerificationLevel** indica si el nivel de comprobación permitido para los mensajes enviados al y desde el proveedor de hospedaje. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si este nivel no se especifica, el mensaje será rechazado por ser no comprobable.

## Comprobar la replicación del almacén de administración central actualizada

Los cambios que haya realizado usando cmdlets en las secciones anteriores se aplican automáticamente al Servidor perimetral y generalmente tardan menos de un minuto en replicarse. Puede validar el estado de replicación y, a continuación, confirmar que los cambios se han aplicado a su Servidor perimetral usando los siguientes cmdlets.

Para comprobar las actualizaciones de replicación, en un servidor interno de la implementación de Lync Server, ejecute el siguiente cmdlet:

    Get-CsManagementStoreReplicationStatus

Para confirmar que se han aplicado los cambios, en el Servidor perimetral, ejecute el siguiente cmdlet:

    Get-CsHostingProvider -LocalStore

## Vea también

#### Otros recursos

[Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)


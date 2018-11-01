---
title: "Configurar servidor perim. para integración con mensajería unif. Exchange hospedada"
TOCTitle: Configurar el servidor perimetral para la integración con la mensajería unificada de Exchange hospedada
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48277085
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el servidor perimetral para la integración con la mensajería unificada de Exchange hospedada

 

_**Última modificación del tema:** 2015-01-23_

Para proporcionar capacidades de correo de voz a los usuarios de Lync Server 2013 en la mensajería unificada de Mensajería unificada de Exchange (UM) hospedada, debe llevar a cabo las tareas de configuración siguientes en el servidor perimetral:

  - Configure el servidor perimetral para la federación.

  - Replicar los datos del Almacén de administración central en el servidor perimetral y comprobar la replicación.

  - Crear un proveedor de hospedaje en el servidor perimetral.

Para ver más detalles, consulte la documentación del Shell de administración de Lync Server correspondiente a los siguientes cmdlets:

  - [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration)

  - [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

> [!IMPORTANT]  
> Debe crear un registro SRV de DNS externo para el servicio Exchange de hospedaje antes de realizar estos pasos. Para más información, consulte <a href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange</a>.



## Para configurar el servidor perimetral para la federación.

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsAccessEdgeConfiguration para configurar el servidor para la federación. Por ejemplo, ejecute lo siguiente:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.
    
      - **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.
    
      - **EnablePartnerDiscovery** especifica si Lync Server usará registros DNS para intentar detectar los dominios de socios no incluidos en la lista de dominios permitidos de Active Directory. Si está definido en False, Lync Server 2013 solo establecerá relaciones de federación con dominios que figuren en la lista de dominios admitidos. Este parámetro es necesario si se usa el enrutamiento del servicio DNS. En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.

## Para replicar los datos en el servidor perimetral y comprobar la replicación.

  - Compruebe que la replicación de datos en el servidor perimetral se haya completado. Para conocer el procedimiento, consulte [Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

## Para crear un proveedor de hospedaje en el servidor perimetral

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsHostingProvider** para configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear, en este ejemplo es **Fabrikam.com** . Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.
    
      - **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True** .
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
        

        > [!NOTE]
        > Antes de establecer <CODE>EnableSharedAddressSpace</CODE> en True, intente resolver internamente el registro SRV de federación. Si esto no es posible, debe crear los registros _sipfederationtls._tcp.&lt;domain&gt; y _sip._tls.&lt;domain&gt; en el servidor DNS interno. Estos registros deberían apuntar a la dirección IP externa de la interfaz de acceso del servidor perimetral.

    
      - **HostsOCSUsers** indica si se usará el proveedor de hospedaje para hospedar las cuentas de Lync Server 2013. Si es **False** , el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje, que en este ejemplo es **proxyserver.fabrikam.com** . Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **IsLocal** indica si el servidor proxy que usa el proveedor de hospedaje está incluido en la topología de Lync Server 2013.
    
      - **VerficationLevel** indica el nivel de comprobación permitido para los mensajes enviados a y desde el proveedor de hospedaje. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje será rechazado por ser no comprobable.

## Vea también

#### Tareas

[Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  

#### Conceptos

[Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  

#### Otros recursos

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)


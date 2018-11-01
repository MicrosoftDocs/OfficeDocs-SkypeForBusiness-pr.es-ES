---
title: Configurar compatibilidad de federación para un dominio de Lync Online
TOCTitle: Configurar compatibilidad de federación para un dominio de Lync Online
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48274580
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar compatibilidad de federación para un dominio de Lync Online

 

_**Última modificación del tema:** 2012-11-01_

Para federar con un cliente de Microsoft Lync Online 2010, se deben seguir estos pasos:

  - Configurar compatibilidad para el dominio del cliente de Lync Online 2010 (por ejemplo, contoso.onmicrosoft.com). Tal como se especificó en la sección [Requisitos previos para federar con un cliente de Lync Online](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de esta documentación, ya debe haber habilitado la federación para su organización. Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados. Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización. Si no habilitó la detección de dominio, debe agregar el nombre de dominio del cliente de Lync Online a su lista de dominios permitidos. Puede agregar un nombre de dominio mediante Panel de control de Lync Server o mediante la ejecución del cmdlet de **New-CSAllowedDomain**. Para obtener información sobre el uso de Panel de control de Lync Server, incluido cómo habilitar la detección de dominios, consulte [Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación sobre operaciones. Para obtener información sobre el uso del cmdlet de **New-CSAllowedDomain** para agregar un dominio, vea [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain) en la documentación sobre operaciones.
    

    > [!NOTE]
    > Un cliente de Lync Online puede tener varios dominios. Si desea federar con más de uno de los dominios, debe configurar la compatibilidad para cada dominio individual con el que desea admitir la federación, y el administrador del cliente de Lync Online debe habilitar la federación para cada uno de los dominios que se van a federar.



  - Configure la compatibilidad para el proveedor de hospedaje del dominio de cliente de Lync Online 2010 con el que desea federar. Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.
    

    > [!NOTE]
    > Este paso es necesario solamente para federación con un dominio de un cliente de Lync Online, no para federación con cualquier dominio que se implementa localmente en la ubicación de un socio federado.



## Para configurar compatibilidad para un proveedor de hospedaje

1.  Desde un Servidor front-end, Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.
    
      - **Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en una situación de espacio de direcciones SIP compartido (dominio dividido).
    
      - **HostsOCSUsers** indica si se usará el proveedor de hospedaje para hospedar las cuentas de Lync Server. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está contenido dentro de su topología de Lync Server.
    
    Para obtener información sobre el uso de este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider) en la documentación sobre operaciones.


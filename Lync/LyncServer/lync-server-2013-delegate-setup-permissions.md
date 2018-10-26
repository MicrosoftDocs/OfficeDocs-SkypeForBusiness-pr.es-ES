---
title: 'Lync Server 2013: Delegar permisos de instalación'
TOCTitle: Delegar permisos de instalación
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48276230
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Delegar permisos de instalación en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

Si no desea otorgar la pertenencia al grupo Admins. del dominio a los usuarios o grupos que implementen Lync Server 2013, puede permitir a los miembros del grupo RTCUniversalServerAdmins ejecutar el cmdlet **Enable-CsTopology** de Windows PowerShell en servidores que ejecuten Lync Server 2013. De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins no pueden ejecutar este cmdlet. Para conceder permisos para ejecutar **Enable-CsTopology** en servidores que ejecuten Lync Server, use el cmdlet **Grant-CsSetupPermission** y especifique una unidad organizativa donde se encuentren los objetos de equipo del servidor que ejecuta Lync Server 2013.

La preparación del dominio que tiene lugar al instalar Lync Server no agrega automáticamente los permisos con los que los miembros del grupo RTCUniversalServerAdmins pueden iniciar el cmdlet Enable-CsTopology. Esto quiere decir que, de forma predeterminada, se debe ser un administrador del dominio para poder habilitar una topología. Si desea otorgar a los miembros del grupo RTCUniversalServerAdmins el derecho para habilitar una topología, inicie el cmdlet Grant-CsSetupPermissions. Además, deberá iniciarlo en cada uno de los contenedores de Active Directory que hospeden PC en los que se ejecute Lync Server.

Recuerde que este cmdlet solo concede permisos al grupo RTCUniversalServerAdmins; por lo tanto, no se puede usar para conceder permisos a otros grupos de seguridad ni a usuarios individuales.


> [!NOTE]
> <STRONG>Enable-CsTopology</STRONG> es el principal cmdlet para permitir a los miembros del grupo RTCUniversalServerAdmins configurar e implementar Lync Server 2013.



## Para conceder al grupo RTCUniversalServerAdmins la posibilidad de ejecutar Enable-CsTopology

1.  Inicie sesión en un servidor como miembro del grupo Admins. del dominio para el dominio en que el usuario delegado ejecutará **Enable-CsTopology**.

2.  Abra el Shell de administración de Lync Server 2013. El Shell de administración de Lync Server 2013 se instala automáticamente en cada Servidor front-end o en cualquier equipo donde se hayan instalado las herramientas administrativas de Lync Server 2013. Para obtener más información sobre el Shell de administración de Lync Server 2013, vea [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md) en la documentación sobre operaciones.

3.  Ejecute el cmdlet siguiente en el Shell de administración de Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    

    > [!NOTE]
    > Si la unidad organizativa no es de nivel superior, debe proporcionar el nombre de dominio completo.

    
    En el ejemplo siguiente, la unidad organizativa es "Lync Servers" y se encuentra en el dominio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com


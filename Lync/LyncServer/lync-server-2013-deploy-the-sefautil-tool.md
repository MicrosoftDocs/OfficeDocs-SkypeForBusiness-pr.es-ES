---
title: Implementar la herramienta SEFAUtil
TOCTitle: Implementar la herramienta SEFAUtil
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945659(v=OCS.15)
ms:contentKeyID: 52061976
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar la herramienta SEFAUtil

 

_**Última modificación del tema:** 2016-12-08_

Para implementar y administrar la respuesta de llamadas en grupo, use la herramienta del kit de recursos SEFAUtil. Esta herramienta forma parte de las herramientas del kit de recursos de Lync Server 2013. Para instalar SEFAUtil, debe tener un grupo de aplicaciones de confianza en la topología, especificar SEFAUtil como aplicación de confianza y habilitar la topología.

> [!IMPORTANT]  
> Instale el SDK de la API administrada de comunicaciones unificadas (UCMA) de Microsoft 3.0 Core en los equipos donde planee ejecutar la herramienta SEFAUtil.



Puede ejecutar SEFAUtil en cualquier Grupo de servidores front-end de la implementación.


> [!NOTE]
> Para más información sobre cómo ejecutar SEFAUtil, vea la entrada de blog de Technet sobre cómo poner en marcha SEFAutil, en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?linkid=278940</A>.



## Para implementar SEFAUtil

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  La herramienta SEFAUtil solo se puede ejecutar en un equipo que forme parte de un grupo de aplicaciones de confianza. Si es preciso, defina un grupo de aplicaciones de confianza para el Grupo de servidores front-end donde planee ejecutar SEFAUtil. En la línea de comandos, ejecute:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Defina la herramienta SEFAUtil como aplicación de confianza. En la línea de comandos, ejecute:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    

    > [!NOTE]
    > Si es preciso, puede usar otro puerto.



5.  Habilite la topología con los cambios. En la línea de comandos, ejecute:
    
        Enable-CsTopology

6.  Instale las herramientas del kit de recursos de Lync Server 2013 en un Servidor front-end del grupo de aplicaciones de confianza que creó en el paso 3.

7.  Compruebe que la herramienta SEFAUtil funcione correctamente, tal como se indica:
    
    1.  Ejecute la herramienta desde el símbolo del sistema de Windows con privilegios de administrador para que aparezca la configuración de reenvío de llamadas de un usuario en la implementación.
        

        > [!NOTE]
        > La herramienta se encuentra en \Archivos de programa\Microsoft Lync Server 2013\Reskit.

    
    2.  Muestre la configuración de reenvío de llamadas de un usuario. En la línea de comandos, ejecute:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Aparecerá la configuración de reenvío de llamadas del usuario.


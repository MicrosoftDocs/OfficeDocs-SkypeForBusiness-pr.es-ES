---
title: "Comprobar o configurar la autenticación y certificación en directorios virtuales IIS"
TOCTitle: Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48274999
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013

 

_**Última modificación del tema:** 2012-05-25_

Realice el siguiente procedimiento para configurar la certificación en los directorios virtuales de Servicios de Internet Information Server (IIS) o comprobar que la certificación se ha configurado correctamente. Realice el siguiente procedimiento en cada servidor que ejecute IIS en el grupo de servidores interno de Lync Server y en los servidores opcionales Directoro Grupo de directores.


> [!NOTE]
> El procedimiento siguiente define un procedimiento para solicitar un certificado combinado que se utiliza a todos los efectos en Lync Server, el sitio web interno y el sitio web externo en IIS. El Lync Server 2010 ha presentado una serie de cmdlets Shell de administración de Lync ServerWindows PowerShell con el objetivo expreso de gestionar la solicitud, la importación y la asignación de certificados. Este procedimiento supone que existe una entidad de certificación (CA) implementada internamente que puede procesar la solicitud. Si utiliza certificados públicos para sus propósitos de Lync Server, o su CA requiere una solicitud fuera de línea, consulte la sintaxis detallada acerca de este tema para obtener información acerca del –Salida parámetro. <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



## Configuración de la autenticación y los certificados en los directorios virtuales IIS

1.  Para completar con éxito lo siguiente, debe haber iniciado sesión en el equipo ( Servidor front-end o Director) en el que están instalados los servicios web y ser un administrador local. Debe tener permisos de **lectura** e **inscripción** en la entidad de certificación a la que solicitará los certificados, si la entidad de certificación es la entidad de certificación de su organización. No necesitará permisos de la entidad de certificación si configura y envía una solicitud de certificado fuera de línea.

2.  Haga clic en **Inicio**, elija **Todos los programas**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

3.  En **Administrador de Internet Information Services (IIS)**, seleccione **ServerName**. En **Vista Características**, seleccione **Certificados de servidor**, haga clic con el botón secundario y seleccione **Abrir característica**.
    
    > [!TIP]  
    > En la Vista Características de certificados de servidor, si hay certificados asignados al servidor, aparecerán aquí. Si hay un certificado que coincide con los requisitos del sitio web externo en IIS, puede volver a utilizar este certificado. Para ver un certificado, haga clic con el botón secundario en el certificado y seleccione <strong>Ver…</strong>
    


4.  En el Servidor front-end o el Director para el que está solicitando el certificado, haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Microsoft Lync Server 2013** y, a continuación, haga clic en **Shell de administración de Lync Server**.

5.  En Shell de administración de Lync Server, escriba lo siguiente:
    
        Get-CsCertificate
    
    El resultado es una lista de los certificados que están actualmente en el servidor del almacén de certificados personales del equipo. Ten en cuenta que en el certificado combinado (es decir, donde los servicios web internos y los servicios web externos predeterminados están utilizando el mismo certificado), verá que la propiedad de uso se rellenará con predeterminado, WebServicesInternal y WebServicesExternal. Además, la propiedad huella digital será la misma para cada uno de los tipos de uso. En este ejemplo se muestra un resultado de ejemplo de Get-CsCertificate:
    
    ![Información de Get-CsCertificate sobre el estado de scert actual](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Información de Get-CsCertificate sobre el estado de scert actual")

6.  En Shell de administración de Lync Server, escriba lo siguiente:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Donde el comando completo aparecería como en el siguiente ejemplo:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    > [!TIP]  
    > De modo predeterminado, Request-CsCertificate rellenará el nombre de asunto con el nombre del servidor o del grupo de servidores y rellenará las entradas en el nombre alternativo del asunto con el servidor FQDN, el grupo de servidores FQDN, los FQDN de URL simples y los FQDN de los servicios web internos y externos. Esto lo hace haciendo referencia al documento de topología de su implementación. Si falta un valor y ha especificado el parámetro –Verbose, se le notificará que los valores calculados y reales de los nombres alternativos son diferentes, pero no se le informará de los valores que faltan. Se le proporcionará el valor calculado completo al que hace referencia el cmdlet. Utilice la cadena de nombres alternativos calculados en el resultado para volver a solicitar un nuevo certificado que incluya todos los valores
    
    
    ![Salida de la solicitud de certificado usando Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Salida de la solicitud de certificado usando Request-CsCertifica")

7.  En Shell de administración de Lync Server, escriba lo siguiente:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Donde el comando completo aparecería como en el siguiente ejemplo:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    para\>El resultado del cmdlet Set-CsCertificate mostrará que se ha asignado el mismo certificado (identificado por la huella digital del certificado) para el uso predeterminado, WebServicesExternal y WebServicesInternal u
    
    ![Salida desde Set-CsCertificate en WebExt de IIS](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Salida desde Set-CsCertificate en WebExt de IIS")

## Para comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS

1.  Haga clic en **Inicio**, elija **Todos los programas**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

2.  En **Administrador de Internet Information Services (IIS)**, expanda **ServerName** y después haga lo mismo con **Sitios**.

3.  Haga clic con el botón secundario en **Sitio web externo de Lync Server** y, a continuación, haga clic en **Modificar enlaces**

4.  Compruebe que https está asociado al puerto 4443 y haga clic en **https**.

5.  Seleccione la entrada HTTPS, haga clic en **Editar** y, a continuación compruebe que Lync Server WebServicesExternalCertificate está enlazado a este protocolo. Compare la huella digital del cmdlet Set-CsCertificate para asegurar que el certificado esperado está correctamente asociado con el enlace HTTPS.

## Vea también

#### Otros recursos

[Get-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)


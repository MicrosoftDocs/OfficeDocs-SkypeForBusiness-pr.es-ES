---
title: 'Lync Server 2013: Modificación de certificados para movilidad'
TOCTitle: Modificación de certificados para movilidad
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48275239
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de certificados para movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-20_

Para admitir conexiones seguras entre su entorno Lync y sus clientes móviles, los certificados de Capas de sockets seguros (SSL) del Grupo de directores, el Grupo de servidores front-end y el proxy inverso van a tener que actualizarse con algunas entradas de nombre alternativo (SAN). Si necesita comprobar más detalles sobre los requisitos de certificado para la movilidad, vea la sección Requisitos de certificado en [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente necesitará obtener nuevos certificados de la entidad de certificación con las entradas SAN adicionales incluidas y luego agregar esos certificados siguiendo los pasos de este artículo.

Por supuesto, antes de comenzar, normalmente es una buena idea conocer los nombres alternativos del sujeto que ya tienen sus certificados. Si no está seguro de lo que ya se ha configurado, hay muchas formas de descubrirlo. Aunque dispone de la opción para ejecutar el **Get-CsCertificate** y otros comandos de PowerShell para ver esta información (que repasaremos abajo), de forma predeterminada se truncarán esos datos, por lo que puede que no llegue ver todas las propiedades que necesita. Para ver bien el certificado y todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento Certificados (que también se repasa más abajo) o simplemente puede comprobar el Asistente para implementar Lync Server.

Como se indica anteriormente, los siguientes pasos le guiarán por el proceso de actualización de los certificados mediante Shell de administración de Lync Server y MMC. Si le interesa usar el Asistente para certificados del Asistente para implementar Lync Server para ello, puede consultar [Configurar los certificados para el director en Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) con respecto al director o el grupo de directores, si configuró uno (es posible que no lo haya configurado). Para el servidor front-end o el grupo front-end, le interesará consultar [Configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).

Una última cosa a tener en cuenta es que puede tener de forma predeterminada un solo certificado en su entorno de Lync Server 2013 o tener certificados separados de forma predeterminada (es decir, todo menos los servicios web), WebServicesExternal y WebServicesInternal. Sea cual sea su configuración, estos pasos deben ayudarle.

## Para actualizar los certificados con nuevos nombres alternativos del sujeto mediante el Shell de administración de Lync Server

1.  Debe iniciar sesión en Lync Server 2013 mediante una cuenta con derechos y permisos de administrador. Además, si está ejecutando **Request-CsCertificate** de PowerShell en los pasos 12 y siguientes, la cuenta debe tener derechos para a la Entidad de certificación (CA) especificada.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para poder asignar un certificado actualizado, deberá averiguar qué certificados se han asignado al servidor y para qué tipo de uso. En la línea de comandos, escriba lo siguiente:
    
        Get-CsCertificate

4.  Compruebe en los resultados del paso anterior si se ha asignado un solo certificado para varios usos o un certificado distinto para cada uso. Mire el parámetro Use para averiguar cómo se usa un certificado. Compare el parámetro Thumbprint de los certificados mostrados para ver si el mismo certificado tiene varios usos. Vigile el parámetro Thumbprint.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** mostró un certificado con Use de Default, otro con Use de WebServicesInternal y otro con Use de WebServicesExternal y todos ellos tenían el mismo valor de Thumbprint, en la línea de comandos, debe escribir:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado distinto para cada uso (por lo que el valor de Thumbprint que comprobó anteriormente es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **Set-CsCertificate** con varios tipos, como en el ejemplo anterior. En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado (o los certificados), haga clic en **Inicio** y en **Ejecutar…**. Escriba MMC para abrir Microsoft Management Console.

7.  En el menú MMC, seleccione **Archivo**, **Agregar o quitar complemento…** y Certificados. Haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.

8.  Si este es el servidor donde se encuentra el certificado, seleccione **Equipo local**. Si el certificado se encuentra en otro equipo, debe seleccionar **Otro equipo** y luego escriba el nombre de dominio completo del equipo o haga clic en **Examinar** en **Escriba el nombre de objeto a seleccionar** y escriba el nombre del equipo. Haga clic en **Comprobar nombres**. Cuando se resuelva el nombre del equipo, se subrayará. Haga clic en **Aceptar** y luego en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.

9.  Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en él con el botón derecho y seleccione **Abrir**.

10. En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre del sujeto del certificado seleccionando **Sujeto**. Se mostrarán el nombre del sujeto asignado y las propiedades asociadas.

11. Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**. Aquí aparecerán todos los nombres alternativos del sujeto asignados. De manera predeterminada, los nombres alternativos del sujeto encontrados aquí son de tipo **Nombre de DNS**. Debería ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS \[A o, en el caso de IPv6, AAAA\]):
    
      - Nombre de grupo para este grupo o nombre del servidor si no es un grupo
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de direcciones URL simples, normalmente reunión y marcación
    
      - Nombres de servicios web internos y externos (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), basados en las selecciones realizadas en Generador de topologías y las selecciones de servicios web invalidados.
    
      - Si ya están asignados, los registros lyncdiscover.\<dominiosip\> y lyncdiscoverinternal.\<dominiosip\>.
    
    El último elemento es lo que más le interesa; si hay una entrada SAN de lyncdiscover y lyncdiscoverinternal.
    
    Repita los pasos si debe comprobar varios certificados. Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.

12. Si falta un nombre alternativo del sujeto del servicio Detección automática, realice lo siguiente:
    
      - En el símbolo de la línea de comandos de Shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe utilizar el parámetro DomainName. Cuando use el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Thumbprint” es la huella digital mostrada para el certificado que acaba de emitir.

13. Cuando faltan los SAN de Detección automática internos al usar certificados independientes en Default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo de la línea de comandos de Shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando use el parámetro DomainName, debe utilizar un prefijo adecuado para los FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Cuando falta un nombre alternativo del sujeto de Detección automática externo, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Cuando use el parámetro DomainName, debe usar un prefijo adecuado para los FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar los tipos de los certificados individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Thumbprint” es la huella digital mostrada para los certificados individuales que acaba de emitir.
    

    > [!NOTE]
    > Solo tenga en cuenta que los pasos 12 y 13 deben ejecutarse únicamente si la cuenta que los ejecuta tiene acceso a la Entidad de certificación con los permisos adecuados. Si no puede iniciar sesión con una cuenta que tenga esos permisos o está usando una Entidad de certificación pública o remota para sus certificados, debería solicitarlos mediante el Asistente de implementación de Lync Server, como se explica anteriormente en este artículo.



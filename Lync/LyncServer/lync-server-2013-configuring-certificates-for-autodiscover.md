---
title: Configurar certificados para la detección automática
TOCTitle: Configurar certificados para la detección automática
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945617(v=OCS.15)
ms:contentKeyID: 52061600
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados para la detección automática

 

_**Última modificación del tema:** 2012-12-12_

Los certificados para el Grupo de directores, el Grupo de servidores front-end y el proxy inverso requieren entradas de nombre alternativo del sujeto para admitir conexiones seguras con clientes de Lync.


> [!NOTE]
> Puede usar el cmdlet <STRONG>Get-CsCertificate</STRONG> para ver información sobre los certificados asignados actualmente. Sin embargo, la vista predeterminada trunca las propiedades del certificado y no muestra todos los valores de la propiedad SubjectAlternativeNames. Puede usar los cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate y <STRONG>Set-CsCertificate</STRONG> para ver alguna información y solicitar y asignar certificados. Sin embargo, no es el mejor método si no está seguro de las propiedades de los nombres alternativos del sujeto (SAN) del certificado actual. Para ver el certificado y todos los miembros de propiedad, se sugiere utilizar el complemento Certificados de <EM>Microsoft Management Console (MMC)</EM> o usar la Asistente para la implementación de Lync Server. En la Asistente para la implementación de Lync Server, puede usar el Asistente para certificados para ver las propiedades del certificado. Los procedimientos para ver, solicitar y asignar un certificado con el Shell de administración de Lync Server y <EM>Microsoft Management Console (MMC)</EM> se detallan en los siguientes procedimientos. Para usar la Asistente para la implementación de Lync Server, vea los detalles aquí si ha implementado el Director opcional o el Grupo de directores: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configurar los certificados para el director en Lync Server 2013</A>. Para el Servidor front-end o el Grupo de servidores front-end, vea los detalles aquí: <A href="lync-server-2013-configure-certificates-for-servers.md">Configurar certificados para servidores en Lync Server 2013</A><BR>Los primeros pasos de este procedimiento son los pasos de preparación, a fin de orientarlo en cuanto a qué papel juegan los certificados actuales. De manera predeterminada, los certificados no tendrán una entrada lyncdiscover.&lt;dominiosip&gt; o lyncdiscoverinternal.&lt;nombre de dominio interno&gt;, a menos que haya instalado previamente los servicios de movilidad o haya preparado sus certificados por anticipado. Este procedimiento usa el nombre de dominio SIP de ejemplo 'contoso.com' y el nombre de dominio interno de ejemplo 'contoso.net'.<BR>La configuración predeterminada del certificado para Lync Server 2013 y Lync Server 2010 es usar un único certificado (llamado 'Default') con los propósitos Default (para todos los efectos, excepto para los servicios web), WebServicesExternal y WebServicesInternal. Una configuración opcional es usar certificados independientes para cada propósito. Puede administrar los certificados con los cmdlets Shell de administración de Lync Server y Windows PowerShell o con el Asistente para certificados de la Asistente para la implementación de Lync Server.



## Para actualizar los certificados con nuevos nombres alternativos del sujeto mediante el Shell de administración de Lync Server

1.  Inicie sesión en el equipo usando una cuenta con derechos y permisos de administrador.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Averigüe qué certificados se han asignado al servidor y para qué tipo de uso. Esta información es necesaria en el paso siguiente para asignar el certificado actualizado. En la línea de comandos, escriba:
    
        Get-CsCertificate

4.  Compruebe en los resultados del paso anterior si se ha asignado un solo certificado para varios usos o un certificado distinto para cada uso. Mire el parámetro Use para averiguar cómo se usa un certificado. Compare el parámetro Thumbprint de los certificados mostrados para ver si el mismo certificado tiene varios usos.

5.  Actualice el certificado. En la línea de comandos, escriba:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Por ejemplo, si el cmdlet **Get-CsCertificate** ha mostrado un certificado con Use de Default, otro con Use de WebServicesInternal y otro con Use de WebServicesExternal, y todos tienen el mismo valor de Thumbprint, en la línea de comandos, escriba:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Importante:**
    
    Si se asigna un certificado distinto para cada uso (el valor de Thumbprint es diferente para cada certificado), es importante que no ejecute el cmdlet **Set-CsCertificate** con varios tipos. En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso. Por ejemplo:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Para ver el certificado, haga clic en **Inicio** y en **Ejecutar…**. Escriba MMC para abrir Microsoft Management Console.

7.  En el menú MMC, seleccione **Archivo**, **Agregar o quitar complemento…** y Certificados. Haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.

8.  Si el certificado se encuentra en este equipo, seleccione **Equipo local**. Si el certificado se encuentra en otro equipo, seleccione **Otro equipo**, escriba el nombre de dominio completo del equipo o haga clic en **Examinar**. En **Escriba el nombre de objeto para seleccionar**, escriba el nombre del equipo. Haga clic en **Comprobar nombres**. Cuando se resuelva el nombre del equipo, se subrayará. Haga clic en **Aceptar** y luego en **Finalizar**. Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.
    
    > [!IMPORTANT]  
    > Si el certificado no aparece en la consola, asegúrese de no haber seleccionado Usuario o Servicio. Debe seleccionar Equipo; de lo contrario, no podrá encontrar el certificado apropiado.
    


9.  Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en él con el botón secundario y seleccione **Abrir**.

10. En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre del sujeto del certificado seleccionando **Sujeto**. Se mostrarán el nombre del sujeto asignado y las propiedades asociadas.

11. Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**. Aparecerán todos los nombres alternativos del sujeto asignados. De manera predeterminada, los nombres alternativos del sujeto que se encuentran en la propiedad son de tipo **Nombre de DNS**. Debería ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS \[A o, en el caso de IPv6, AAAA\]):
    
      - Nombre de grupo para este grupo o nombre del servidor si no es un grupo
    
      - Nombre del servidor al que está asignado el certificado
    
      - Registros de direcciones URL simples, normalmente reunión y marcación
    
      - Nombres de servicios web internos y externos (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), basados en las selecciones realizadas en la Generador de topologías y las selecciones de servicios web invalidados.
    
      - Si ya están asignados, los registros lyncdiscover.\<dominiosip\> y lyncdiscoverinternal.\<dominiosip\>.
    
    El último elemento es lo que más le interesa; si hay una entrada SAN de lyncdiscover y lyncdiscoverinternal.
    
    Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.

12. Si falta un nombre alternativo del sujeto del servicio Detección automática, es decir, lyncdiscover.\>nombre de dominio\> y lyncdiscoverinternal.\<nombre de dominio\> (en función de si se trata de un certificado externo o de uno interno), y usa un único certificado Default para los tipos Default, WebServicesInternal y WebServiceExternal, haga lo siguiente:
    
      - En el símbolo de la línea de comandos de Shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe utilizar el parámetro DomainName. Cuando use el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Por ejemplo:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Para asignar el certificado, escriba lo siguiente:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Thumbprint” es la huella digital mostrada para el certificado que acaba de emitir.

13. Cuando faltan los nombres alternativos del sujeto de Detección automática internos al usar certificados independientes en Default, WebServicesInternal y WebServicesExternal, haga lo siguiente:
    
      - En el símbolo de la línea de comandos de Shell de administración de Lync Server, escriba:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Cuando falta un nombre alternativo del sujeto de Detección automática externo, en la línea de comandos, escriba:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Para asignar los tipos de los certificados individuales, escriba lo siguiente:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Donde “Thumbprint” es la huella digital mostrada para los certificados individuales que acaba de emitir.


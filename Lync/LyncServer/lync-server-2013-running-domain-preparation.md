---
title: 'Lync Server 2013: Ejecutar la preparación del dominio'
TOCTitle: Ejecutar la preparación del dominio
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48276076
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar la preparación del dominio para Lync Server 2013

 

_**Última modificación del tema:** 2013-04-16_

Puede usar el programa de instalación o los cmdlets del Shell de administración de Lync Server para preparar los dominios. El cmdlet que prepara un dominio es **Enable-CsAdDomain**.

La preparación del dominio es el último paso de la preparación de Servicios de dominio de Active Directory para Lync Server 2013.

## Para preparar dominios durante la instalación

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  En el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar la Asistente para la implementación de Lync Server.

3.  Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

4.  En **Paso 5: Preparar dominio actual** , haga clic en **Ejecutar** .

5.  En la página **Preparar el dominio** , haga clic en **Siguiente** .

6.  En la página **Ejecución de comandos** , busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro** .

7.  En la columna **Acción** , expanda **Preparación de dominio** , busque algún Resultado de ejecución **\<Correcto\>** al final de cada tarea para comprobar que la preparación del dominio se haya completado correctamente, cierre el archivo de registro y haga clic en **Finalizar** .

8.  Espere a que se complete la replicación de Active Directory o fuerce la replicación en todos los controladores de dominio indicados en el complemento Sitios y servicios de Active Directory para el controlador de dominio raíz del bosque.

## Para usar cmdlets para preparar el dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  En el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar la Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí** .
    
    3.  El cuadro de diálogo de instalación de Lync Server 2013 le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar** .
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar** . El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Por ejemplo:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si no especifica el parámetro Domain, el valor predeterminado es el dominio local.

5.  Compruebe que la preparación del dominio se ha realizado correctamente. Ejecute:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Por ejemplo:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuyas opciones de configuración globales no se han migrado al contenedor de configuración), deberá definir un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de AD&nbsp;DS.

    
    Si no especifica el parámetro **Domain**, el valor predeterminado es el dominio local.
    
    Este cmdlet devuelve un valor de **LC\_DOMAINSETTINGS\_STATE\_READY** si la preparación del dominio se ha realizado correctamente.

## Vea también

#### Tareas

[Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  

#### Otros recursos

[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)


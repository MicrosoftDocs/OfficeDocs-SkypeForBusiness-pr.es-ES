---
title: 'Lync Server 2013: Ejecutar la preparación del bosque'
TOCTitle: Ejecutar la preparación del bosque
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48276227
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar la preparación del bosque para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Puede utilizar el programa de instalación o los cmdlets de Shell de administración de Lync Server para preparar el bosque. El cmdlet que prepara el bosque es **Enable-CsAdForest**.

Después de preparar el bosque, debe comprobar que la configuración global se haya replicado antes de llevar a cabo la preparación del dominio.

## Para preparar el bosque durante la instalación

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo de administradores de la empresa para el dominio raíz del bosque.

2.  Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación.

3.  Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

4.  En **Paso 3: Preparar bosque actual** , haga clic en **Ejecutar** .

5.  En la página **Preparar el bosque** , haga clic en **Siguiente** .
    

    > [!NOTE]
    > El proceso de preparación del bosque permite elegir dónde desea instalar los grupos universales para Lync Server 2013. Elija una ubicación que respete los requisitos de su organización.



6.  En la página **Ejecución de comandos** , busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro** .

7.  En la columna **Acción** , expanda **Preparar el bosque** , compruebe que el resultado de la ejecución sea **\<Correcto\>** al final de cada tarea para asegurarse de que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar** .

8.  Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento **Sitios y servicios de Active Directory** del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación en los sitios se produzca en cuestión de minutos.

## Para usar cmdlets en la preparación del bosque

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo Admins. del dominio en el dominio raíz del bosque.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  En el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar la Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí** .
    
    3.  El cuadro de diálogo de instalación de Lync Server 2013 le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar** .
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar** . El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Por ejemplo:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local. Si se crearon grupos universales previamente en un dominio que no es el dominio predeterminado, debe especificar el parámetro GroupDomain explícitamente.

5.  Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento **Sitios y servicios de Active Directory** del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio.

6.  Compruebe que la preparación del bosque se ha realizado correctamente. Ejecute:
    
        Get-CsAdForest 
    
    Este cmdlet devuelve un valor de **LC\_FORESTSETTINGS\_STATE\_READY** si la preparación del bosque se ha realizado correctamente.

## Vea también

#### Tareas

[Usar cmdlets para invertir la preparación del bosque para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  

#### Otros recursos

[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)


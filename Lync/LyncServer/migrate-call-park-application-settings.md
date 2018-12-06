---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
TOCTitle: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49888922
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar la configuración de la aplicación de estacionamiento de llamadas

 

_**Última modificación del tema:** 2012-10-19_

La migración de la aplicación Estacionamiento de llamadas de Lync Server 2010 a Lync Server 2013 incluye el aprovisionamiento del grupo de servidores de Lync Server 2013 con cualquier archivo de música en espera personalizado que se haya cargado en Lync Server 2010, la restauración de la configuración del nivel de servicio y la nueva asignación de destino de todas las órbitas de estacionamiento de llamadas al grupo de servidores de Lync Server 2013. Si se han configurado los archivos de música en espera personalizados en el grupo de servidores de Lync Server 2010, estos archivos se tienen que copiar al nuevo grupo de servidores de Lync Server 2013. Además, se recomienda que realice copias de seguridad de cualquier archivo de música en espera personalizado de estacionamiento de llamadas desde Lync Server 2010 a otro destino para conservar una copia de seguridad independiente de cualquier archivo de música en espera personalizado que se haya cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio desde un almacén de archivos de grupo de servidores de Lync Server 2010 a un almacén de archivos de Lync Server 2013, use el comando **Xcopy** con los siguientes parámetros:

```
Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
```
```
Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Cuando se han copiado todos los archivos de audio personalizados al almacén de archivos de Lync Server 2013, se deben configurar los valores de aplicación de estacionamiento de llamadas del grupo de servidores de Lync Server 2013 y se deben reasignar los intervalos de órbitas de estacionamiento de llamadas que están asociados al grupo de servidores de Lync Server 2010 al grupo de servidores de Lync Server 2013.

Los valores de aplicación de estacionamiento de llamadas incluyen el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de la música en espera, los intentos de recogida de llamadas máximos y la solicitud de tiempo de espera. Debe administrar los valores de aplicación de estacionamiento de llamadas mediante el Shell de administración de Lync Server para ejecutar el cmdlet **Set-CsCpsConfiguration**. No puede administrar los valores de aplicación de estacionamiento de llamadas mediante el Panel de control de Lync Server.

**Volver a configurar los valores de servicio de estacionamiento de llamadas**

1.  Desde el servidor front-end de Lync Server 2013, abra la Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    

    > [!NOTE]
    > Si sus valores de aplicación de estacionamiento de llamadas de Lync Server 2013 son idénticos a la configuración de Lync Server 2010 heredada, puede omitir la ejecución de este paso. Si los valores de aplicación de estacionamiento de llamadas son diferentes de los entornos de Lync Server 2013 y Lync Server 2010, use el cmdlet siguiente como plantilla para actualizar dichos cambios.

    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas desde el grupo de servidores de Lync Server 2010 hasta el grupo de servidores de Lync Server 2013, puede usar el Panel de control de Lync Server o el Shell de administración de Lync Server.

**Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante el panel de control de Lync Server**

1.  Abra Panel de control de Lync Server.

2.  En el panel izquierdo, seleccione **Características de voz**.

3.  Seleccione la pestaña **Estacionamiento de llamadas**.

4.  Para cada intervalo de órbita de estacionamiento de llamada asignado a un grupo de servidores de Lync Server 2010, edite la configuración del **FQDN del servidor de destino** y seleccione el grupo de servidores de Lync Server 2013 que procesará las solicitudes de estacionamiento de llamadas.

5.  Seleccione **Confirmar** para guardar los cambios.

**Vuelva a asignar todos los intervalos de órbita de estacionamiento de llamadas mediante el Shell de administración de Lync Server**

1.  Abra Shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Get-CsCallParkOrbit
    
    Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación. Se deben volver a asignar todas las órbitas del estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo de servidores de Lync Server 2010.
    
    Para volver a asignar los intervalos de órbita de estacionamiento de llamadas de Lync Server 2010 al grupo de servidores de Lync Server 2013, en la línea de comandos, escriba lo siguiente:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Tras reasignar todos los intervalos de órbita de estacionamiento de llamadas al grupo de servidores de Lync Server 2013, se completará el proceso de migración para la aplicación de estacionamiento de llamadas y el grupo de servidores de Lync Server 2013 administrará todas las solicitudes de estacionamiento de llamadas futuras.


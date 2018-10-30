---
title: "Crear o modificar un conjunto de opciones de configuración de Lync Phone Edition"
TOCTitle: "Créat. ou mod. d’une collection de param. de conf. de Lync Phone Edition"
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49889221
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de un conjunto de opciones de configuración de Lync Phone Edition

 

_**Última modificación del tema:** 2013-02-23_

Cuando se instala Lync Server, se obtiene una colección global de configuraciones de Lync Phone Edition. Estas configuraciones se aplican a todos los dispositivos de su implementación que ejecuten Lync Phone Edition. Además de poder cambiarlas en cualquier momento, también se puede configurar una colección nueva que se aplique a los dispositivos de un sitio específico. Las opciones de configuración de sitio tienen preferencia sobre las globales.

Las opciones de configuración están constituidas por: el nombre y el ámbito (de sitio o global) de la colección, la opción de seguridad SIP, el nivel de registro, el nivel de calidad del servicio (QoS) de voz, la opción del bloqueo del teléfono y, por último, los detalles del bloqueo del teléfono, que definen la longitud del número de identificación personal (PIN) de desbloqueo y el tiempo que el teléfono permanece inactivo hasta que se bloquea.

## Para crear una colección de opciones de configuración de Lync Phone Edition o editar las de una colección existente

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, después, en el botón de navegación **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, realice alguna de las operaciones siguientes:
    
      - Para crear una colección de opciones de configuración de Lync Phone Edition, haga clic en **Nuevo**, seleccione un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y realice los cambios que desee.
    
      - Para editar alguna configuración de una colección existente, haga clic en la colección, haga clic en el menú **Editar**, en **Mostrar detalles** y realice los cambios que desee.
        
        > [!TIP]  
        > Para volver a usar las opciones en configuración predeterminadas en la colección global, haga clic en ella, haga clic en el menú <strong>Editar</strong>, en <strong>Eliminar</strong> y, después, en <strong>Aceptar</strong>. Con esto no se eliminará la colección global, sino que solo se restablecerán las opciones predeterminadas.
        


5.  Haga clic en **Confirmar**.

## Para crear opciones de configuración de Lync Phone Edition con los cmdlets de Shell de administración de Lync Server

También puede crear opciones de configuración de Lync Phone Edition (solo en el ámbito de sitio) con el Shell de administración de Lync Server y el cmdlet **New-CsUCPhoneConfiguration**. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear opciones de configuración de Lync Phone Edition que usen los valores predeterminados

  - Este comando crea un conjunto de opciones de configuración de teléfonos para UC para el sitio Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (aparte del parámetro obligatorio Identity) en el comando anterior, la colección nueva de opciones de configuración usará los valores predeterminados para todas sus propiedades.

## Para crear un único valor de propiedad al crear opciones de configuración de Lync Phone Edition

  - Para crear opciones de configuración que usen valores de propiedad distintos, simplemente tiene que incluir el valor del parámetro y el parámetro adecuados. Por ejemplo, para crear una colección de opciones de configuración de teléfonos para UC que utilicen el bloqueo del teléfono de forma predeterminada, use un comando como este:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## Para cambiar varios valores de propiedad al crear opciones de configuración de Lync Phone Edition

  - Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Este comando, por ejemplo, sirve para aplicar el bloqueo del teléfono y para establecer una longitud mínima de 8 dígitos del PIN:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

Para más información, consulte [New-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUCPhoneConfiguration).

## Vea también

#### Tareas

[Eliminación de un conjunto existente de opciones de configuración de Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configuración de la seguridad para Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Exigir el bloqueo del teléfono](lync-server-2013-enforce-phone-locking.md)


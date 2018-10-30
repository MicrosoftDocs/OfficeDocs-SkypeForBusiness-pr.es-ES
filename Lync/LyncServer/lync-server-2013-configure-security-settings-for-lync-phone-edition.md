---
title: Configuración de la seguridad para Lync Phone Edition
TOCTitle: Configuración de la seguridad para Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48275598
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la seguridad para Lync Phone Edition

 

_**Última modificación del tema:** 2013-02-23_

Ayúdenos a mejorar la seguridad de los dispositivos que ejecutan Lync Phone Edition a través de los ajustes de bloqueo del teléfono y la configuración de seguridad SIP.

## Para configurar la seguridad de Lync Phone Edition

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de seguridad.

5.  En **Editar configuración de dispositivo**, en **Seguridad SIP**, especifique el nivel de seguridad SIP. El nivel predeterminado, que recomendamos utilizar, es **Alto**.

6.  En **Editar configuración de dispositivo**, en **Bloqueo del teléfono**, active o desactive la casilla **Forzar bloqueo del dispositivo** (activada de forma predeterminada) y especifique la longitud mínima del PIN (6 caracteres de forma predeterminada) y el tiempo de espera (10 minutos de forma predeterminada). Recomendamos que se utilicen los valores predeterminados o bien que se incremente la longitud del PIN y se disminuya el tiempo de espera.
    

    > [!NOTE]
    > Para más información, vea <A href="lync-server-2013-enforce-phone-locking.md">Exigir el bloqueo del teléfono</A>.



## Configurar la seguridad de los teléfonos con Lync Phone Edition con los cmdlets del Shell de administración de Lync Server

También puede administrar los ajustes de seguridad con el Shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration**. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para modificar el modo de seguridad SIP

  - Este comando establece como Medio el modo SIPSecurityMode para la colección global de ajustes de los teléfonos para UC. El nivel de seguridad SIP también se puede definir como Bajo o Alto (valor predeterminado).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## Para modificar la longitud mínima del PIN

  - En este ejemplo, se modifican todos los ajustes de los teléfonos para UC de modo que se establece la longitud mínima del PIN en 7 dígitos.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

Para más información, vea [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Vea también

#### Conceptos

[Administrar la autenticación de Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)


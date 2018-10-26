---
title: Configuración de la telefonía para un usuario
TOCTitle: Configuración de la telefonía para un usuario
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48275090
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la telefonía para un usuario

 

_**Última modificación del tema:** 2012-11-01_

La configuración telefónica forma parte de la configuración individual de una cuenta de usuario que se puede configurar en Panel de control de Lync Server para el usuario (es decir, si el usuario individual está habilitado para Lync Server 2013 y la organización admite la telefonía).

Entre las opciones de telefonía de usuario de Lync Server se incluyen las siguientes:

  - **Audio y vídeo deshabilitados**   El usuario no puede realizar llamadas con audio y vídeo.

  - **Solo de equipo a equipo**   El usuario solo puede realizar llamadas de audio o vídeo de un equipo a otro.

  - **Telefonía IP empresarial**   El usuario puede usar la infraestructura de Lync Server 2013 para enrutar todas las llamadas entrantes y realizadas. También puede realizar llamadas de equipo a equipo.

  - **Control remoto de llamadas**   El usuario puede usar Lync Server 2013 para controlar el teléfono de escritorio y realizar llamadas de equipo a equipo.

Para obtener información detallada acerca de cómo configurar la telefonía para una organización, consulte [Configuración de la telefonía para un usuario](lync-server-2013-configure-telephony-for-a-user.md) y [Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.

## Para configurar la telefonía para una cuenta de usuario específica

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee modificar.

6.  En el menú **Editar**, haga clic en **Modificar**.

7.  En **Telefonía**, siga este procedimiento:
    
      - Para deshabilitar las llamadas de audio y vídeo del usuario, haga clic en **Audio y vídeo deshabilitados**.
    
      - Para habilitar las comunicaciones de audio de equipo a equipo para el usuario, pero no el control remoto de llamadas ni la Telefonía IP empresarial, haga clic en **Solo de equipo a equipo**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.
    
      - Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Lync Server 2010, de acuerdo con la clase de directiva de servicio, incluida la comunicación de audio de equipo a equipo, haga clic en **Telefonía IP empresarial**. En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario. Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.
    
      - Para habilitar el control remoto de llamadas, que permite al usuario controlar su línea de teléfono de escritorio desde Lync Server 2013 para realizar llamadas de equipo a equipo y de equipo a teléfono, haga clic en **Control remoto de llamada**. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.

## Vea también

#### Otros recursos

[Modificación de las propiedades de cuentas de usuario](lync-server-2013-modifying-user-account-properties.md)


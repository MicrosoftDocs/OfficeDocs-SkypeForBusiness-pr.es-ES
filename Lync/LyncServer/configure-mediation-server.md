---
title: Configurar servidor de mediación
TOCTitle: Configurar servidor de mediación
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48275319
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar servidor de mediación

 

_**Última modificación del tema:** 2016-12-08_

En este procedimiento se detallan los pasos necesarios para configurar el grupo Lync Server 2013 para utilizar el servidor de mediación Lync Server 2013 en lugar del servidor de mediación Office Communications Server 2007 R2 heredado.

Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos RTCUniversalServerAdmins y Admins. del dominio. También es posible delegar los derechos y permisos de administrador apropiados para agregar roles de servidor. Puede obtener información detallada sobre los permisos para la configuración de delegados en la documentación referente a la implementación del servidor Standard Edition o del servidor Enterprise Edition. Para otros cambios de configuración, únicamente se necesita ser miembro del grupo RTCUniversalServerAdmins.


> [!NOTE]
> Para obtener la información más reciente sobre la búsqueda de puertas de enlace RTC cualificadas, sistemas IP-PBX y servicios de enlace troncal SIP que funcionen con Lync Server 2013, consulte "Microsoft Unified Communications Open Interoperability Program" en <A href="http://go.microsoft.com/fwlink/?linkid=206015%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=206015&amp;clcid=0xC0A</A>.



## Configurar el servidor de mediación mediante el Generador de topologías

1.  Abrir una topología existente desde el Generador de topologías

2.  En el panel de la izquierda, navegue a **Puertas de enlace RTC**.

3.  Haga clic con el botón secundario en **Puertas de enlace RTC** y, a continuación, haga clic en **Nueva puerta de enlace IP/RTC**.

4.  Complete la página **Definir nueva puerta de enlace IP/RTC** con la siguiente información:
    
      - Indique el FQDN de puerta de enlace o la dirección IP. El FQDN de la puerta de enlace es obligatorio si la puerta de enlace utiliza el protocolo TLS.
    
      - Acepte el valor predeterminado de la opción **Puerto de escucha para la puerta de enlace IP/RTC** o, si se ha modificado, especifique el nuevo puerto de escucha.
    
      - Establezca el **Protocolo de transporte SIP**.

5.  En el panel de la izquierda, navegue al **grupo de servidores front-end Enterprise Edition** o al **servidor Standard Edition**.

6.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

7.  En **Servidor de mediación**, defina los **Puertos de escucha**.

8.  A continuación, asocie la puerta de enlace RTC recién creada seleccionándola y haciendo clic en **Agregar**.

9.  En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.

10. En el menú **Acciones**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

11. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.


> [!NOTE]
> Es importante completar el tema siguiente, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Cambiar rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</A> para asegurarse de que las rutas de voz señalen al servidor de mediación correcto.



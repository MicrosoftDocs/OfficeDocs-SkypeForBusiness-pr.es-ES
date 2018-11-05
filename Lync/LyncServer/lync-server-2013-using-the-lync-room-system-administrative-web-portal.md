---
title: "Lync Server 2013 : ut. du portail web d’admin. du syst. de salle Lync"
TOCTitle: Usar el portal web administrativo de Lync Room System
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62269031
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar el portal web administrativo de Lync Room System en Lync Server 2013

 

_**Última modificación del tema:** 2014-11-10_

Después de implementar LRS en el servidor, puede comprobar el estado de todas las salas de LRS iniciando sesión en el portal web administrativo de LRS desde un explorador.

## Iniciar sesión

1.  Vaya a la siguiente dirección URL:
    
    https://\<fe-server\>/lrs

2.  Escriba las credenciales de la cuenta LRSSupport o de una cuenta que se haya agregado a su grupo de seguridad LRSSupportAdminGroup.

![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión en el portal de administración del sistema Lync Room")

## Página de resumen del portal web administrativo de LRS

La página de resumen ofrece la siguiente información sobre todas las salas de LRS implementadas en el servidor:

  - **Etiqueta**: el nombre personalizado que el administrador le pone a la sala. La etiqueta se puede establecer en el portal haciendo clic en el nombre de la sala.

  - **Mantenimiento**: el estado de mantenimiento de la sala, que se deriva del estado de mantenimiento global de la sala; este se va en la sección Mantenimiento de la página Configuración de sala.

  - **Próxima reunión**: la fecha y hora en que está programada la siguiente reunión.

  - **Versión de LRS, fabricante, modelo**: estos valores están preestablecidos en LRS. En función del fabricante, estos campos pueden dejarse en blanco.

  - **Última actualización**: muestra la última vez que se actualizó la página web.

![Vista resumida del portal de administración del sistema Lync Room](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Vista resumida del portal de administración del sistema Lync Room")

## Información sobre la sala de LRS

La sección de información de salas del portal le permite ver y configurar salas de LRS individuales. Contiene cuatro secciones: Configuración, Detalles, Registro y Mantenimiento.

## Configuración

En la sección de configuración, puede establecer la contraseña, la etiqueta de la sala y los valores de volumen predeterminados de la sala. Si configura estas opciones, los cambios solo se replican al reiniciar la consola de LRS.

![Configuración de salones del portal de administración del sistema Lync Room](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configuración de salones del portal de administración del sistema Lync Room")

## Detalles

La sección de detalles ofrece un resumen de solo lectura de las opciones de la sala de LRS, incluyendo: la hora de la última actualización; próxima reunión; últimas actualizaciones, mantenimiento y calibración; opciones predeterminadas de altavoz, micrófono y timbre; versión; URI de SIP; número de pantallas y detalles sobre cada pantalla; estado y actividad.

![Vista en detalle del portal de administración del sistema Lync Room](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Vista en detalle del portal de administración del sistema Lync Room")

## Registro

La sección de registro se puede usar para recopilar remotamente registros y guardarlos en una ubicación especificada. También puede reiniciar la consola de LRS (interfaz de usuario de LRS) o reiniciar el sistema completo.

![Registro de salones del portal de administración del sistema Lync Room](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registro de salones del portal de administración del sistema Lync Room")

## Mantenimiento

La sección de mantenimiento ofrece una indicación visual del mantenimiento de la conexión, el dispositivo de audio, el dispositivo de vídeo, el estado de resiliencia y el dispositivo de pantalla de Lync Server.

![Estado de los salones del portal de administración del sistema Lync Room](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Estado de los salones del portal de administración del sistema Lync Room")

## Notas adicionales sobre el portal web administrativo


> [!NOTE]
> <UL>
> <LI>
> <P>Por razones de seguridad, el portal web administrativo cierra su sesión automáticamente cada 15&nbsp;minutos.</P>
> <LI>
> <P>Los cambios de configuración se aplican después de reiniciar el sistema de LRS.</P>
> <LI>
> <P>Las notificaciones del portal web administrativo de LRS son adhesivas, es decir, que no desaparecen.</P>
> <LI>
> <P>Las notificaciones solo aparecen al actualizar la página.</P>
> <LI>
> <P>El estado de las salas de LRS aparece cuando se actualiza la página.</P>
> <LI>
> <P>Si la contraseña de la cuenta LRSApp expira, no podrá ver el estado de las salas. Configure la contraseña de la cuenta de usuario LRSApp para que nunca expire o asegúrese de actualizar la contraseña cuando falte poco tiempo para que expire.</P>
> <LI>
> <P>El portal web administrativo de LRS solo es compatible con las implementaciones locales.</P></LI></UL>



## Solución de problemas

## ¿Por qué no puedo iniciar sesión en el portal web administrativo?

  - Al abrir https://localhost/lrs, verá la página de inicio de sesión, pero cuando escriba las credenciales, no podrá iniciar sesión. En este caso, debe abrir https://FQDNofFEserver/lrs para iniciar sesión en el portal web administrativo.

  - Si la máquina desde la que intenta obtener acceso al portal web administrativo está en un grupo de trabajo, "http://" no servirá. Deberá usar "https".

## ¿Por qué no veo LRS en el portal web administrativo?

  - Asegúrese de que tiene cuentas de LRS en su implementación y de que se han creado según las recomendaciones de implementación del portal web administrativo de LRS. Asegúrese de que las cuentas de LRS se aprovisionen usando Enable-CsMeetingRoom (y no Enable-CsUser) en el servidor de Lync.

  - Si ha creado cuentas de LRS y no las ve en el portal web administrativo, recopile los registros de servidor usando la Herramienta de registro de Lync Server con el componente **MeetingPortal** seleccionado y luego envíelos a su contacto de soporte técnico de LRS.

## ¿Por qué no veo el estado de LRS en el portal web administrativo?

  - Asegúrese de que la cuenta de usuario LRSApp esté habilitada para SIP.

  - Si sigue teniendo problemas, recopile el archivo **Trace.log** en el sistema de LRS de D:\\Tracing\\LRSAdminLogs\\ y envíelo a su contacto de soporte técnico de LRS.


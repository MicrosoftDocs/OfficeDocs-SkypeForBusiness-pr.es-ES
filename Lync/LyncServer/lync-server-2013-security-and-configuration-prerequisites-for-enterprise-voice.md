---
title: "Lync Server 2013: Requisitos seguridad y configuración para telefonía IP empresarial"
TOCTitle: Requisitos previos de seguridad y configuración para telefonía IP empresarial
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48274531
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Compruebe que la infraestructura cumple con los siguientes requisitos previos de seguridad, configuración de usuario y hardware específico del escenario.

## Derechos administrativos e infraestructura de certificados

Asegúrese de que el entorno está configurado de forma que se usan los siguientes grupos de usuarios administrativos e infraestructura de certificados durante el proceso de implementación de Enterprise Voice.

  - Los administradores que implementen Enterprise Voice deben ser miembros del grupo RTCUniversalServerAdmins.

  - Los administradores encargados de las tareas de configuración deben poseer los derechos apropiados:
    
      - **CsVoiceAdministrator:** este rol de administrador permite realizar tareas de configuración de voz, administrar aplicaciones de voz y asignar directivas de voz a usuarios finales.
    
      - **CsUserAdministrator:** este rol de administrador permite administrar las propiedades de usuario, como, por ejemplo, habilitar Enterprise Voice para un usuario. Este rol de administrador también sirve para asignar directivas específicas de usuario (menos la directiva de archivado), mover usuarios y administrar teléfonos y dispositivos analógicos de área común.
    
      - **CsAdministrator:** este rol de administrador permite realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.
    

    > [!NOTE]
    > La delegación permite que un mayor número de administradores participe en la implementación de Lync Server sin requerir un acceso innecesario a los recursos.



  - Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.
    

    > [!NOTE]
    > Para obtener información detallada sobre los requisitos de certificado en Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de la infraestructura de certificados para Lync Server 2013</A> en la documentación de planeación.



## Configuración de usuario

Si, durante la implementación del front-end, instaló el servidor de mediación junto con cada grupo de servidores front-end o servidor Servidor Standard Edition, la configuración de usuario de Enterprise Voice se habrá establecido automáticamente al instalarse los archivos de dichos roles de servidor.

En caso de que esté implementando la carga de trabajo de Enterprise Voice por primera vez, antes de iniciar el proceso, designe un número de teléfono principal por cada usuario para el que tenga previsto habilitar Enterprise Voice. En tanto que administrador, es responsable de asegurarse de que este número sea único. Antes de proceder a la implementación, todos los números de teléfono principales deben estar normalizados (esto es, deben tener el formato adecuado) y haberse copiado en la propiedad **URI de línea** de cada usuario mediante el Panel de control de Lync Server.


> [!NOTE]
> Si desea ver ejemplos de números de teléfono principales necesarios en una implementación de Enterprise Voice, consulte la sección sobre <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Planes de marcado y reglas de normalización en Lync Server 2013</A> de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación de planeación.



## Pasos siguientes: Instalar archivos o configurar la conectividad RTC

Una vez confirmados los requisitos previos de software y entorno para Enterprise Voice, puede usar el siguiente contenido para:

  - Instalar el servidor de mediación tal y como se describe en [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero únicamente si tiene intención de implementar un servidor de mediación o un grupo de servidores independiente, ya que los servidores de mediación se instalan como parte del proceso de implementación del grupo de servidores front-end o del Servidor Standard Edition cuando se instalan juntos.

  - Iniciar las tareas de configuración necesarias para enrutar llamadas para usuarios de Enterprise Voice según se explica en [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).


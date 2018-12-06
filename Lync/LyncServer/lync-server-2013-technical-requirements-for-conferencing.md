---
title: 'Lync Server 2013: Requisitos técnicos para conferencias'
TOCTitle: Requisitos técnicos para conferencias
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48274996
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En Lync Server 2013, la funcionalidad de conferencia de acceso telefónico local, conferencia A/V, conferencia de mensajería instantánea (MI) y conferencia web siempre se ejecutan en Servidores front-end.

En esta sección se describen detalladamente los requisitos de hardware y software de estos servidores, junto con la combinación admitida.

La conferencia de acceso telefónico local es una característica que incluye una variedad de componentes. Algunos de los componentes son específicos de las conferencias de acceso telefónico local y algunos son componentes de Telefonía IP empresarial. Esta sección describe los requisitos para los componentes que son específicos de las conferencias de acceso telefónico local. Para obtener más información acerca del Servidor de mediación y los requisitos de puerta de enlace de la red telefónica conmutada (RTC), consulte [Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md) y [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación sobre planificación.

## Requisitos de hardware

Puesto que la conferencia web y la conferencia A/V se combinan con el Servidor front-end, los requisitos de hardware del servidor son los mismos que para los Servidores front-end. Para obtener información sobre los requisitos de hardware, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad. Los siguientes componentes necesarios para conferencias de acceso telefónico local también tienen los mismos requisitos de hardware como Servidores front-end:

  - Servicio de aplicaciones

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

Los requisitos de hardware para un Servidor front-end son los mismos que para muchos otros roles de servidor de Lync Server 2013 y se describen en la siguiente tabla.

## Requisitos de software

Puesto que la conferencia web y la conferencia A/V se combinan con el Servidor front-end, los requisitos de software del servidor son los mismos que para los Servidores front-end. Para obtener más información sobre los requisitos previos de software, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación relativa a la compatibilidad.

Para la conferencia web, Lync Server 2013 también requiere Office Web Apps y el Servidor Office Web Apps (conocido anteriormente como WAC Server) para administrar presentaciones de PowerPoint. Para obtener información detallada, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Para las conferencias de acceso telefónico local, el Servicio de aplicaciones, el Aplicación Operador de conferencia y el Aplicación de anuncio de conferencia tienen los mismos requisitos de sistema operativo que los Servidores front-end. Para obtener más información acerca de los requisitos de software, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

El Aplicación Operador de conferencia y el Aplicación de anuncio de conferencia requieren que el tiempo de ejecución de Windows Media Format esté instalado en Servidores front-end. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de audio de Windows Media (WMA) que se usan para la música en espera, nombres registrados y avisos. Excepto para Windows Server 2012 y Windows Server 2012 R2, el tiempo de ejecución de Windows Media Format se instala automáticamente como parte de la experiencia de escritorio de Windows al ejecutar el programa de instalación, pero es posible que deba reiniciar el equipo. Por lo tanto, recomendamos que lo instale como parte de la experiencia de escritorio de Windows, que incluye el tiempo de ejecución de Windows Media Format antes de ejecutar el programa de instalación. Windows Server 2012 y Windows Server 2012 R2 requieren Microsoft Media Foundation.

## Requisitos de puerto para conferencias de acceso telefónico local

En la tabla siguiente se describen los puertos usados por las conferencias de acceso telefónico local. Si usa un equilibrador de carga, asegúrese de que está configurado para los puertos usados por las aplicaciones que se ejecutarán en el grupo.

Estos puertos son configuraciones predeterminadas que se pueden cambiar mediante el cmdlet **Set-CsApplicationServer**. Para información sobre este cmdlet, vea la documentación de Shell de administración de Lync Server.


> [!NOTE]
> Todas las instancias de la misma aplicación en un grupo de servidores usan el mismo puerto de escucha de SIP.



### Puertos usados por las conferencias de acceso telefónico local

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de puerto</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Usado por el Aplicación Operador de conferencia para solicitudes de escucha SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usado por el Aplicación de anuncio de conferencia para solicitudes de escucha SIP</p></td>
</tr>
</tbody>
</table>


## Clientes admitidos para conferencias de acceso telefónico local

Puede usar al siguiente cliente para programar conferencias locales que admiten el acceso telefónico local:

  - Complemento para conferencia en línea para Lync 2013 (instalado automáticamente al instalar Lync 2013 o Asistente)

## Requisitos de Página Configuración de conferencia de acceso telefónico local

Página Configuración de conferencia de acceso telefónico local admite combinaciones de los sistemas operativos y los exploradores web que se describen en la tabla siguiente.


> [!NOTE]
> Las versiones de 32 bits y 64 bits de los sistemas operativos son compatibles.



### Sistemas operativos y exploradores web compatibles

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Explorador web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


## Requisitos de archivo de audio para conferencias de acceso telefónico local

Lync Server 2013 no admite la personalización de mensajes de voz ni de la música para conferencias de acceso telefónico local. No obstante, si por motivos profesionales muy necesarios debe cambiar los archivos de audio predeterminados, consulte el artículo 961177 de Microsoft Knowledge Base, [Cómo personalizar mensajes de voz o los archivos de música de marcado en conferencias de audio en Microsoft Office Communications Server 2007 R2 en](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

También puede usr la utilidad de administración [Mensajes de voz del operador de conferencia de Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880), que permite a los administradores reemplazar los mensajes de voz predeterminados utilizados cuando el autor de una llamada de teléfono se une a una reunión de Lync con mensajes personalizados para proporcionar una introducción diferente de la reunión. Los mensajes de voz personalizados pueden instalarse en un servidor que está ejecutando Lync Server 2010 o Lync Server 2013, Standard Edition o Enterprise.

El Aplicación Operador de conferencia y el Aplicación de anuncio de conferencia tienen los siguientes requisitos para archivos de música en espera, nombre grabado y mensajes de audio:

  - Formato de archivo de audio de Windows Media (WMA)

  - Mono de 16 bits

  - 48 kbps CBR 2 pasos (velocidad de bits constante)

  - Nivel de voz a -24DB

## Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local deben tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios de empresa (es decir, los usuarios que tienen credenciales de cuentas de Servicios de dominio de Active Directory y Lync Server en su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para tener acceso a conferencias como usuario autenticado.


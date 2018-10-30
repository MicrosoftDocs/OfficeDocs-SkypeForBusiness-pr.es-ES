---
title: Requisitos de la aplicación de la Tienda Windows de Lync
TOCTitle: Requisitos de la aplicación de la Tienda Windows de Lync
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ823129(v=OCS.15)
ms:contentKeyID: 52061647
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de la aplicación de la Tienda Windows de Lync

 

_**Última modificación del tema:** 2016-12-08_

Las organizaciones con una implementación local de Lync Server deben cumplir los siguientes requisitos para admitir Aplicación de la Tienda Windows de Lync.


> [!NOTE]
> Para Lync Server 2010, ejecute la actualización acumulativa para Lync Server 2010 de febrero de 2012 (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) o posterior en todos los servidores. Para permitir que los usuarios participen en reuniones, ejecute la actualización acumulativa para Lync Server 2010 de octubre de 2012 (disponible en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) en todos los servidores.



  - Habilite los servicios de detección automática, Lync Web App y vales web en el servidor.

  - Habilite la autenticación de certificados en Servidor front-end o Grupo de servidores front-end. (El proceso de registro del usuario en Servidor front-end o Grupo de servidores front-end suele denominarse registrador). Para obtener información detallada, consulte [Creación de opciones de configuración de un registrador](lync-server-2013-create-registrar-configuration-settings.md).

  - Publique los registros de recurso de alias DNS (CNAME) para el servicio de detección automática.

  - Ya no hace falta asegurarse de que el punto de distribución de la lista de revocación de certificados (CRL) correspondiente a los certificados emitidos a Lync Server apunte a un recurso HTTP en vez de a un recurso LDAP, pero sí hay que asegurarse de que los equipos cliente tengan instaladas las últimas actualizaciones de Windows.

  - Configure proxies HTTP en la empresa para permitir tráfico HTTP relacionado con Lync Server. Agregue excepciones para los servicios de detección automática, Lync Web App y vales web, si es necesario.

  - En Clientes, instale Windows 8.1 y la versión más reciente de Aplicación de la Tienda Windows de Lync para solucionar un problema con el inicio de sesión que, en general, ocurre cuando se utilizan varios dominios (por ejemplo, si el URI de SIP es **userA@domainZ.com** pero el servidor perimetral es **sip.domainX.com**).

Si la organización está suscrita a Lync Online u Office 365 y va a usar su propio nombre de dominio, debe llevar a cabo algunos pasos adicionales para configurar la red para la detección automática de los servidores de Lync. Los requisitos de la configuración de red son los mismos para Aplicación de la Tienda Windows de Lync y Lync en dispositivos móviles. Siga las instrucciones “Configurar la red” en el artículo Wiki de Office 365: “Configurar dispositivos móviles de Lync,” disponible en [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

## Vea también

#### Conceptos

[Implementar la aplicación de la Tienda Windows de Lync](lync-server-2013-deploying-lync-windows-store-app.md)


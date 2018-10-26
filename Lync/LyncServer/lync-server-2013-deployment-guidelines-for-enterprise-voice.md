---
title: 'Lync Server 2013: Instrucciones para la implementación de la telefonía IP empresarial'
TOCTitle: Instrucciones para la implementación de la telefonía IP empresarial
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48275934
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instrucciones para la implementación de la telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Este tema describe los requisitos previos y otras instrucciones que debe tener en cuenta al planear la implementación de la carga de trabajo de Lync Server 2013 y Telefonía IP empresarial.

## Requisitos previos de implementación

Para obtener una experiencia óptima al implementar Telefonía IP empresarial, asegúrese de que la infraestructura de TI, la red y los sistemas cumplen los siguientes requisitos previos:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y operativo en la red.

  - Tener implementados y operativos todos los servidores perimetrales de la red perimetral, incluidos los servidores perimetrales con Servidor perimetral de acceso, Servicio perimetral A/V, Servicio perimetral de conferencia web y un proxy inverso.

  - Haber creado y habilitado uno o varios usuarios en Lync Server.

  - Se necesita tener instalado Microsoft Exchange Server 2007 Service Pack 1 (SP1) o el último service pack, o bien Microsoft Exchange Server 2010. Una de estas dos opciones es necesaria para integrar Mensajería unificada de Exchange (UM) en Lync Server y para proporcionar notificaciones avanzadas e información de registro de llamadas a los extremos de cliente.

  - Debe haberse designado, normalizado y copiado un número de teléfono principal único en el atributo **msRTCSIP-line** de cada usuario que vaya a habilitarse para Telefonía IP empresarial.
    

    > [!NOTE]
    > Lync Server admite números E.164 y números que no sean de Llamada directa a la extensión (DID). Los números que no son DID se pueden representar con el formato <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> o como una cadena de dígitos, siempre que la extensión privada sea única en toda la empresa. Por ejemplo, el número privado 1001 se puede representar como <STRONG>+1425550100;ext=1001</STRONG> o como <STRONG>1001</STRONG>. Cuando se representa como <STRONG>1001</STRONG>, se espera que este número privado sea único en toda la empresa.



  - Los administradores que implementen Telefonía IP empresarial deben ser miembros del grupo RTCUniversalServerAdmins.

  - Como mínimo, debe estar implementado correctamente Office Communicator 2007. Para usar las nuevas características de esta versión, se implementa Lync 2013.

  - Hay implementada y configurada una infraestructura de clave administrada (MKI) con una infraestructura de entidad de certificación (CA) de Microsoft o de otro fabricante.

  - Cada equipo donde se instale el servidor de mediación deberá:
    
      - Ser miembro de un dominio y estar preparado para Servicios de dominio de Active Directory. Para ver los procedimientos de preparación de Servicios de dominio de Active Directory, vea [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.
    
      - Ejecutar uno de los sistemas operativos siguientes:
        
          -   
            La edición de 64 bits del sistema operativo Windows Server 2008 Standard
        
          -   
            La edición de 64 bits del sistema operativo Windows Server 2008 Enterprise

  - Si la conexión a la red telefónica conmutada (RTC) o central de conmutación (PBX) se realiza por medio de una conexión de multiplexación por división de tiempo (TDM), una o más puertas de enlace RTC deben estar disponibles para la implementación. (Si la conexión se realiza por medio de un tronco SIP, no se necesita ninguna puerta de enlace RTC.)

## Interrupciones de alimentación, de la red o del servicio telefónico

Si se produce una interrupción, un corte u otro tipo de degradación de la alimentación eléctrica, de la red o de los servicios telefónicos en su ubicación, es posible que no funcionen correctamente las características de voz, mensajería instantánea, presencia y otras funciones de Lync Server, así como los dispositivos conectados a Lync Server.

## Enterprise Voice depende de la disponibilidad del servidor y de la operabilidad del cliente VoIP y del hardware

Las comunicaciones de voz con Lync Server dependen de la disponibilidad del software de servidor y del correcto funcionamiento de los clientes de voz o de los dispositivos telefónicos que se conectan al software de servidor.

## Métodos de acceso alternativos a los servicios de emergencia

En aquellas ubicaciones donde instale un cliente de voz (por ejemplo, un equipo que ejecute un cliente de Lync o un dispositivo Lync Phone Edition), se recomienda tener una opción de respaldo para que los usuarios puedan llamar a los servicios de emergencia (por ejemplo, 911 o 999) en el caso de que se produzca un apagón, una degradación de la conectividad de red, una interrupción en el servicio telefónico u otro problema que pueda impedir el funcionamiento de Lync Server, Lync o de los dispositivos Lync Phone Edition. Esas opciones alternativas pueden ser un teléfono conectado a una línea de la red telefónica conmutada estándar o un teléfono móvil.

## Llamadas de emergencia y sistemas telefónicos de varias líneas

El uso de un sistema telefónico de varias líneas (MLTS) podría estar sujeto a leyes estatales o federales de EE. UU., o a las legislaciones de otros países o regiones que requieran que el MLTS proporcione a los servicios de emergencia correspondientes el número de teléfono, la extensión y/o la ubicación física de las personas que llaman a los servicios de emergencia (por ejemplo, cuando se marca un número de emergencia, como el 911 o el 999). En esta versión, Lync Server se puede configurar para facilitar la ubicación física del autor de una llamada al proveedor de servicios de emergencia, según se describe en [Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). El cumplimiento con la legislación sobre MLTS es responsabilidad exclusiva del comprador de Lync Server, el cliente Lync y los dispositivos Lync Phone Edition.


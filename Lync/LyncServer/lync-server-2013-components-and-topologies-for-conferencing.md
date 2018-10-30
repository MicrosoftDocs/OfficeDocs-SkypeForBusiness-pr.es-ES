---
title: 'Lync Server 2013: Componentes y topologías para conferencias'
TOCTitle: Componentes y topologías para conferencias
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48277068
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-04_

Cuando se selecciona la opción de conferencia en Generador de topologías, las conferencias se implementan como parte de Servidor front-end o Servidor Standard Edition. Las conferencias de acceso telefónico y el uso compartido de PowerPoint requieren componentes y configuraciones adicionales. En las secciones siguientes se describen los componentes y las topologías admitidos para las conferencias web, las conferencias A/V y las conferencias de acceso telefónico.

## Componentes admitidos

Los únicos componentes que requieren las conferencias web y las conferencias A/V son Servidores front-end o Servidores Standard Edition de su organización. Para obtener una lista de los requisitos de hardware y software para Servidores front-end y Servidores Standard Edition, vea [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) y [Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 usa Office Web Apps y Servidor Office Web Apps para gestionar el uso compartido y el procesamiento de las presentaciones de PowerPoint. Para obtener información sobre la instalación y configuración de Servidor Office Web Apps, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Además de los requisitos para las conferencias web y A/V, las conferencias de acceso telefónico usan los siguientes componentes de Lync Server 2013:

  - **Servicio de aplicación**    Servicio de aplicaciones proporciona una plataforma para implementar, hospedar y administrar las aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico usan dos aplicaciones de UC que requieren Servicio de aplicaciones: operador de conferencia y anuncio de conferencia. Servicio de aplicaciones se instala y activa de manera predeterminada en cada Servidor front-end de un Grupo de servidores front-end y en cada Servidor Standard Edition cuando se implementa una carga de trabajo de conferencias y se selecciona la opción de conferencias de acceso telefónico.

  - **Aplicación Operador de conferencia**    Aplicación Operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de la red telefónica conmutada (RTC), reproduce avisos e introduce las llamadas en una conferencia A/V. Aplicación Operador de conferencia se instala y activa de manera predeterminada cuando se implementa una carga de trabajo de conferencias y se selecciona la opción de conferencias de acceso telefónico.

  - **Aplicación de anuncio de conferencia**    Aplicación de anuncio de conferencia es una aplicación de comunicaciones unificadas que reproduce tonos y avisos para los participantes de RTC en determinadas acciones como, por ejemplo, cuando los participantes entran o salen de una conferencia, cuando se activa o se desactiva el audio de los participantes, cuando alguien entra en la sala de espera de la conferencia o cuando se bloquea o se desbloquea la conferencia. Aplicación de anuncio de conferencia también es compatible con los comandos de tono de marcado de frecuencia múltiple (DTMF) desde el teclado del teléfono. Aplicación de anuncio de conferencia se instala y activa automáticamente de forma predeterminada cuando se implementa una carga de trabajo de conferencias y se selecciona la opción de conferencias de acceso telefónico.

  - **Página Configuración de conferencia de acceso telefónico local**    Página Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico a conferencias con sus idiomas disponibles, la información de las conferencias asignadas (es decir, de las reuniones que no requieren programación) y los controles DTMF de la conferencia, y es compatible con la administración de números de identificación personal (PIN) y la información de conferencias asignadas. Página Configuración de conferencia de acceso telefónico local se instala automáticamente como parte de Servicios web.

  - **Lync Server 2013, Servidor de mediación y puerta de enlace RTC**   Las conferencias de acceso telefónico requieren un Servidor de mediación para traducir la señalización (y los medios, en algunas configuraciones) entre Lync Server 2013 y la puerta de enlace RTC y una puerta de enlace RTC para traducir la señalización y los medios entre el Servidor de mediación y la puerta de enlace RTC. Para las conferencias de acceso telefónico, debe implementar al menos un Servidor de mediación y al menos uno de los siguientes elementos:
    
      - Puerta de enlace RTC
    
      - Un sistema IP-PBX
    
      - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    

    > [!NOTE]
    > Si está implementando también Telefonía IP empresarial, Servidor de mediación y las puertas de enlace RTC forman parte de la implementación Telefonía IP empresarial. Si no está implementando Telefonía IP empresarial, debe implementar al menos un Servidor de mediación y al menos una puerta de enlace RTC, un sistema IP-PBX o un SBC para las conferencias de acceso telefónico.



  - **Almacenamiento de archivos**   El almacenamiento de archivos se usa para los archivos de audio de los nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **Almacenamiento de usuarios**   El almacenamiento de usuario se emplea para almacenar los PIN de Lync Server 2013 de los usuarios. Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **Panel de control de Lync Server**   Algunas opciones de configuración de acceso telefónico se pueden definir usando Panel de control de Lync Server.

  - **Shell de administración de Lync Server**   Todas las opciones de acceso telefónico local se pueden configurar con cmdlets de Shell de administración de Lync Server. Los cmdlets de Shell de administración de Lync Server están disponibles para implementar, configurar, ejecutar, supervisar y solucionar problemas de Aplicación Operador de conferencia y Aplicación de anuncio de conferencia. Para obtener más información sobre cmdlets específicos, vea la documentación de Shell de administración de Lync Server.

## Topologías admitidas

En Lync Server 2013, el servidor que ejecuta los servicios de conferencias siempre están instalados con Servidores front-end o Servidores Standard Edition. Durante la implementación inicial, Generador de topologías le ofrece la opción de incluir los servicios de conferencia en su topología. También puede usar Generador de topologías para añadir estos servicios a una implementación existente. Si desea más información, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

## Topologías de conferencias de acceso telefónico local

Puede implementar la característica de conferencia de acceso telefónico local en las configuraciones y topologías siguientes:

  - Lync Server 2013Standard Edition

  - Lync Server 2013Enterprise Edition

  - Con o sin Telefonía IP empresarial

Puede implementar Servicio de aplicaciones, Aplicación Operador de conferencia y Aplicación de anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.


> [!NOTE]
> Si implementa la conferencia de acceso telefónico local, deberá implementarla en cada uno de los grupos de servidores en los que se implementen las conferencias de Lync Server 2013. No es necesario asignar números de acceso en cada grupo de servidores, pero debe implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica de nombre registrado cuando un usuario llama a un número de acceso desde un grupo de servidores para unirse a una conferencia de Lync Server 2013 en un grupo de servidores diferente.



## Topologías admitidas para Lync Server 2013 y Office Web Apps

Lync Server 2013 ofrece las siguientes formas de configurar Servidor Office Web Apps. Dependiendo de sus necesidades, puede:

  - **Instalar Lync Server 2013 y Servidor Office Web Apps internamente, detrás del firewall de la organización y en la misma zona de red.** Con esta topología, el acceso externo a Servidor Office Web Apps se facilita a través del servidor de proxy inverso. Tanto Lync Server 2013 como Servidor Office Web Apps (o una granja de Servidor Office Web Apps) están instalados internamente y detrás del firewall de la organización. Lo ideal es instalar Servidor Office Web Apps en la misma zona de red que Lync Server.
    
    Los clientes de Lync externos pueden conectarse a Lync Server 2013 y Servidor Office Web Apps usando un servidor proxy inverso, que es un servidor que toma las solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor de proxy inverso porque se pueden conectar directamente a Servidor Office Web Apps). Esta topología funciona mejor cuando se desea usar una granja de Servidor Office Web Apps dedicada que solo use Lync Server 2013.

  - **Uso de un Servidor Office Web Apps** implementado en el exterior
    
    En esta topología, Lync Server 2013 se implementa internamente y utiliza un Servidor Office Web Apps que se implementa fuera de la zona de red de Lync Server. Esto puede ocurrir cuando Servidor Office Web Apps se comparte con varias aplicaciones de la corporación y se implementa en una red que requiere que Lync Server use la interfaz externa de Servidor Office Web Apps y viceversa.
    
    No necesita instalar un servidor proxy inverso. En lugar de eso, todas las solicitudes del Servidor Office Web Apps al Lync Server 2013 se enrutan a través de su Servidor perimetral. Tanto los clientes de Lync internos como los externos se conectan a Servidor Office Web Apps usando la dirección URL externa.
    
    Si el Servidor Office Web Apps se implementa fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (es decir, perímetro/Internet)** en Generador de topologías. Si desea más información, vea [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe comprobar que los firewall no bloquean los nombres DNS, las direcciones IP y los puertos en el Servidor Office Web Apps, el equilibrador de carga ni Lync Server.


> [!NOTE]
> Otra opción para ofrecer acceso externo a Servidor Office Web Apps es implementar el servidor en la red perimetral. Si se decide a hacerlo, recuerde que para configurar el Servidor Office Web Apps necesita que el equipo servidor sea miembro de su dominio Active Directory. A menos que su directiva de red permita a los equipos de la red perimetral ser miembros del dominio Active Directory, no se recomienda instalar Servidor Office Web Apps en la red perimetral, sino instalar Servidor Office Web Apps en la red interna y ofrecer acceso a usuarios externos a través de su servidor proxy inverso.



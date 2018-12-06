---
title: "Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server para Skype"
TOCTitle: 'Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server para Skype'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn440172(v=OCS.15)
ms:contentKeyID: 59602839
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server 2013 para Skype

 

_**Última modificación del tema:** 2016-12-27_

**P: ¿Qué características se pueden usar entre Microsoft Lync y Skype?**

**R:** Ahora que Skype forma parte de la familia Microsoft, se abren nuevas posibilidades para ampliar los escenarios de comunicaciones unificadas disponibles para los cientos de millones de personas que usan Skype. Esta combinación permitirá a los clientes de Lync conectar y colaborar con proveedores, clientes y socios gracias a la riqueza de Lync y el alcance de Skype.

  - Mensajería instantánea y llamadas de audio y vídeo: llamadas de audio y vídeo y mensajería instantánea federadas entre usuarios de Skype y Lync

  - Compartir la presencia: se puede intercambiar información de presencia entre contactos federados

  - Administración fácil: opciones y controles para configurar las comunicaciones federadas de acuerdo con las directivas y los estándares de la organización

**P: ¿Cuáles son los requisitos para conectar una implementación de Lync con Skype?**

**R:** Tiene licencia para usar la conectividad con Skype si cuenta con una de las opciones siguientes:

  - Lync Server (2010 o 2013) más Licencias de acceso de clientes ("CAL" 2010 o 2013) estándar de Lync Server para los usuarios y/o dispositivos de la organización que se vayan a conectar a Skype. 

  - Lync Online (como licencias independientes o como parte de un conjunto de aplicaciones de Office 365). Sin embargo, este servicio (pic.lync.com) solo sirve para aprovisionar las implementaciones de Lync Server y las implementaciones híbridas de Lync Server y Lync Online. El aprovisionamiento de PIC para Lync Online se hace en el panel de control de Lync Online (LOCP).

**P: ¿Qué tienen que hacer los usuarios finales de Lync para conectar con los contactos de Skype?**

**R:** Cuando un administrador de Lync perteneciente a la organización activa un dominio y habilita las características, los usuarios de Lync pueden agregar contactos de Skype a las listas de contactos que tienen en el cliente de Lync.

**P: ¿Qué tienen que hacer los usuarios finales de Skype para conectar con los contactos de Lync?**

**R:** Los usuarios de Skype que quieran conectar con un usuario de Lync deben tener una cuenta Microsoft asociada con su nombre de usuario de Skype. Con esta cuenta, que se puede habilitar dentro del cliente de Skype, es con la que deben iniciar sesión.

**P: ¿Sigue estando disponible la federación con Windows Live?**

**R:** A partir de octubre de 2012, Microsoft empezó a ayudar a los usuarios de Windows Live Messenger (WLM) a pasarse a Skype con la idea de, finalmente, retirar WLM. Lync seguirá permitiendo la federación con WLM mientras este servicio esté en el mercado, pero no se permitirán más activaciones de dominio de Windows Live. La transferencia de los usuarios de WLM está facilitada por Skype 6.0 para Mac y Windows (publicado el 25 de octubre de 2012), que permite iniciar sesión con una cuenta Microsoft (es decir, con las mismas credenciales de WLM). Al iniciar sesión en Skype, las listas de amigos de WLM se rellenan automáticamente en Skype y los usuarios pueden aprovechar las capacidades ampliadas de comunicación, como llamadas a fijos y móviles, el uso compartido de la pantalla, videollamadas grupales y compatibilidad con una gran variedad de dispositivos. Además, los contactos de Lync federados de los usuarios de WLM siguen la transición a Skype con el resto de sus listas de amigos y la mensajería instantánea entre Skype y Lync estará disponible inmediatamente para estos contactos. Los clientes de Lync no tienen que hacer nada para habilitar la continuidad del servicio.

**P: ¿Sigue estando disponible la federación con Yahoo\! o AOL?**

**A:** La federación con Yahoo\! y AOL está en camino de dejar de existir para los clientes de Lync y Office Communications Server. La posibilidad de Microsoft de ofrecer estos servicios depende del soporte de Yahoo\! y AOL, y los contratos subyacentes con ellos se están rescindiendo gradualmente. Para Yahoo\! y AOL, el servicio seguirá disponible hasta junio de 2014. 

  - Yahoo\!: el servicio seguirá estando disponible hasta junio de 2014 y los clientes todavía necesitan tener una licencia de suscripción de usuario de Public IM Connectivity de Microsoft Lync ("PIC USL"). El 1 de septiembre de 2012, la PIC USL dejó de estar disponible para su compra en los acuerdos nuevos y en las prórrogas de contratos. Los clientes con licencias compradas antes de esta fecha podrán seguir federándose con Yahoo\! hasta la fecha de cierre del servicio o hasta que les expire la licencia. Los clientes que poseen licencias PIC con acuerdos que se extienden hasta fechas posteriores al 30 de junio de 2014 recibirán un crédito proporcional al total de los pagos que abracan el período posterior al 30 de junio de 2014.

  - AOL: el 30 de junio de 2014, el servicio de conectividad de mensajería instantánea de Lync ("PIC") ya no estará disponible. Para limitar las interrupciones de los clientes cuando el servicio finalice, hemos suspendido el aprovisionamiento de dominios de cliente adicionales. Hasta el 30 de junio de 2014, los clientes no tienen que hacer nada para seguir admitiendo comunicaciones federadas con AIM. Después de esta fecha (o antes, en el caso de clientes que quieran proporcionar dominios adicionales), habrá un servicio sustituto disponible directamente desde AOL. Para obtener más información sobre el nuevo servicio de AOL, vea <http://aimenterprise.aol.com/pic.php> (abre una página nueva en AOL.com). 

**P: ¿Puedo probar la conectividad con Skype antes de comprar Lync?**

**R:** No existen versiones de prueba para evaluar la conectividad con Skype, pero animamos a los clientes de Lync con licencias válidas a que se suscriban al servicio para probarlo.

**P: ¿Qué información se necesita para aprovisionar?**

**R:** Para enviar una solicitud de aprovisionamiento bajo una licencia cualificada, necesita los datos siguientes:

  - Número del contrato de Microsoft:
    
      - Soporte para el programa de licencias por volumen de Microsoft: número del contrato del programa de licencias por volumen de Microsoft
    
      - Microsoft Partner Network: id. de asociado de la oficina central
    
      - Contrato de licencias del proveedor de servicios: número de inscripción inicial
    
      - Servicios de alto volumen: número de inscripción de producto

  - Nombres de dominio completos (FQDN) para el servicio perimetral de acceso.
    
      - Se necesita un FQDN para, al menos, un servicio perimetral de acceso.
    
      - Si su organización tiene más de un servidor que ejecute el servicio Access Edge, especifique los FQDN para cada servicio de Access Edge adicional. Importante: Si ha especificado previamente un FQDN para el servicio Access Edge y quiere cambiarlo, la preparación del cambio puede tardar varios días en completarse y puede producir una interrupción del servicio. Para evitarlo, le recomendamos que mantenga el FQDN anterior del servicio de Access Edge.

  - Dominio(s) de Protocolo de inicio de sesión (SIP): este es el sufijo del dominio de la URI del SIP que los usuarios usan actualmente para la mensajería instantánea. Si la organización tiene más de un dominio SIP, indique el sufijo del dominio de todos los dominios usados para la mensajería instantánea. Por ejemplo, para usuario1@contoso.com, especifique contoso.com como dominio SIP; en el caso de usuario1@ejemplo.fabrikam.com, el dominio de SIP sería ejemplo.fabrikam.com.
    

    > [!NOTE]
    > Indique solo el sufijo del dominio para el dominio SIP. No indique ningún FQDN para el dominio SIP, ni siquiera el FQDN del servicio perimetral de acceso.



  - Información de contacto: ponga una dirección de correo para el administrador de cada dominio SIP que especifique.

**P: ¿Cómo se habilita la conectividad entre Lync y Skype en un escenario de dominio dividido?**

**R:** Si tiene un escenario de dominio dividido con Lync Online 2013 y Lync Server local (donde los usuarios en línea y locales usan el mismo dominio SIP), habilite la conectividad entre Lync y Skype siguiendo estos tres pasos en el orden indicado:

1.  Configure la conectividad local entre Lync y Skype como se describe en la Guía para el aprovisionamiento de PIC.

2.  Espere a ver la confirmación de que Microsoft ha aprovisionado el dominio.

3.  Cuando vea la confirmación, use el centro de administración de Lync para activar "comunicaciones externas". Para más información, vea [http://office.microsoft.com/es-es/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/es-es/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

El orden es importante. Tiene que configurar la conectividad local antes de habilitar las comunicaciones en Lync Online. Si se cambia el orden, la información introducida para la plataforma local en <https://pic.lync.com> no se transferirá. Si ya ha configurado Lync Online para las comunicaciones externas con este dominio, tiene que desactivarlo, esperar 24 horas y empezar de nuevo escribiendo primero la información local en <https://pic.lync.com> y luego activando las comunicaciones externas para Lync Online.

**P: ¿Puedo aprovisionar varios FQDN de servicio perimetral de acceso para la conectividad de Skype?**

**R:** Puede aprovisionar hasta diez FQDN de servicio perimetral de acceso con cada solicitud de aprovisionamiento.

**P: ¿Puedo conseguir la lista de direcciones de correo de cuentas Microsoft de la que dispone Microsoft para la organización que solicita el aprovisionamiento?**

**R:** No, estas direcciones se consideran información de identificación personal y no se pueden divulgar.

**P: ¿Cómo agrego a un contacto de Windows Live Messenger cuyo id. contiene un dominio no compatible con Windows Live?**

**R:** Si quiere agregar a un usuario de Windows Live Messenger cuya cuenta o cuyo id. no pertenezcan a un dominio de Windows Live, escriba la dirección con el formato siguiente: \<nombre de usuario\>(\<nombre de dominio\>)@msn.com, donde \<nombre de dominio\> es el nombre del dominio de la dirección de correo del usuario. Por ejemplo, si quisiéramos agregar a ted@contoso.com, usaríamos este formato: ted(contoso.com)@msn.com. Para consultar la lista de dominios que administra Windows Live, vea la sección Dominios compatibles del artículo "Problemas conocidos que se producen con mensajería instantánea pública al instalar Live Communications Server Service Pack 1" en http://support.microsoft.com/?kbid=897567.

**P: ¿Cuánto dura el proceso de aprovisionamiento?**

**R:** El aprovisionamiento puede llevar hasta 30 días.

**P: ¿Cómo se sabe que el aprovisionamiento ha terminado?**

**R:** Microsoft envía una notificación por correo electrónico cuando termina el aprovisionamiento.

**P: ¿Cómo se actualizan la configuración o los detalles de los contactos que envío?**

**R:** Puede actualizar la información en el mismo sitio web que usó para solicitar el aprovisionamiento una vez acabado este proceso. Escriba el número de contrato y luego haga clic en Actualizar servicio.


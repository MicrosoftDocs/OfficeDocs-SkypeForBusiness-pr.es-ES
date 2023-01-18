---
title: Códigos de país de enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este artículo para localizar los códigos de país de ruta multimedia para enrutamiento directo, de modo que pueda seleccionar la ruta de acceso multimedia óptima.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a70dad128987a5fb0df639984be07b623f9ff425
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812677"
---
# <a name="direct-routing-media-path-country-codes"></a>Códigos de país de ruta multimedia de enrutamiento directo

Al elegir una ruta de enrutamiento para elementos multimedia, el enrutamiento directo, de forma predeterminada, asigna siempre un centro de datos basado en la dirección IP pública del controlador de borde de sesión (SBC) y siempre selecciona la ruta más cercana al centro de datos SBC.

Sin embargo, en algunos casos la ruta de acceso multimedia predeterminada podría no ser la ruta de acceso a medios óptima; por ejemplo, una IP pública de un rango de Estados Unidos podría asignarse a una SBC ubicada en Europa. 

Mediante el parámetro -MediaRelayRoutingLocationOverride con los cmdlets de New-CsOnlinePSTNGateway y Set-CsOnlinePSTNGateway, puede especificar la región preferida para el tráfico multimedia. Por ejemplo, el siguiente comando especifica que la región preferida es Alemania:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Tenga en cuenta que Microsoft solo recomienda establecer este parámetro si los registros de llamadas indican claramente que la asignación predeterminada del centro de datos para la ruta de acceso multimedia no usa la ruta de acceso más cercana al centro de datos SBC. 
 
## <a name="country-code-reference-table"></a>Tabla de referencia de código de país

En la tabla siguiente se muestran los valores de código de país para el parámetro -MediaRelayRoutingLocationOverride:

| País         | Código 
|-----------------|--------------------|
| Afganistán     | AF |
| Islas Aland   | AX |
| Albania         | AL |
| Argelia         | DZ |
| Samoa Americana  | COMO |
| Andorra         | AD |
| Angola          | AO |
| Anguila        | AI |
| Antártida      | AQ | 
| Antigua y Barbuda | AG |
| Argentina       | AR |
| Armenia         | SOY |
| Aruba           | AW |
| Australia       | AU |
| Austria         | EN |
| Azerbaiyán      | AZ |
| Bahamas         | BS |
| Baréin         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Belarús         | BY |
| Bélgica         | BE |
| Belice          | BZ |
| Benín           | BJ |
| Bermudas         | BM |
| Bután          | BT |
| Bolivia         | BO |
| Bonaire         | BQ |
| Bosnia y Herzegovina | BA |
| Botsuana        | BW |
| Isla Bouvet   | BV |
| Brasil          | BR |
| Territorio Británico del Océano Índico | E/S |
| Islas Vírgenes Británicas | VG |
| Brunéi          | BN |
| Bulgaria        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Camboya        | KH |
| Camerún        | CM |
| Canadá          | CA |
| Islas Caimán  | KY |
| República Centroafricana | CF |
| Chad            | TD |
| Chile           | CL |
| China           | CN |
| Isla de Navidad | CX |
| Islas Cocos (Keeling) | CC |
| Colombia        | CO |
| Comoras         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Islas Cook    | CK |
| Costa Rica      | CR |
| Côte d'Ivoire   | CI |
| Croacia         | RR. HH. |
| Cuba            | CU |
| Curacao         | CW |
| Chipre          | CY |
| Chequia         | CZ |
| Dinamarca         | DK |
| Yibuti        | DJ |
| Dominica        | DM |
| República Dominicana | HACER |
| Ecuador         | EC |
| Egipto           | EG |
| El Salvador     | SV |
| Guinea Ecuatorial | GQ |
| Eritrea         | ER |
| Estonia         | EE |
| Eswatini        | SZ |
| Etiopía        | ET |
| Islas Malvinas | FK |
| Islas Feroe   | FO |
| Fiyi            | FJ |
| Finlandia         | FI |
| Francia          | FR |
| Guayana Francesa   | GF |
| Polinesia Francesa | PF |
| Territorios Australes Franceses | TF |
| Gabón           | GA |
| Gambia          | GM |
| Georgia         | GE |
| Alemania         | DE |
| Ghana           | GH |
| Gibraltar       | GI |
| Grecia          | GR |
| Groenlandia       | GL |
| Granada         | GD |
| Guadalupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | GY |
| Haití           | HOLA |
| Islas Heard y McDonald | HM |
| Honduras        | HN |
| RAE de Hong Kong   | HK |
| Hungría         | HU |
| Islandia         | ES |
| India           | EN |
| Indonesia       | ID |
| Irán            | IR |
| Irak            | IQ |
| Irlanda         | IE |
| Isla de Man     | MI |
| Israel          | IL |
| Italia           | TI |
| Jamaica         | JM |
| Jan Mayen       | XJ |
| Japón           | JP |
| Jersey          | JE |
| Jordania          | JO |
| Kazajistán      | KZ |
| Kenia           | KE |
| Kiribati        | KI |
| Corea           | KR |
| Kosovo          | XK |
| Kuwait          | KW |
| Kirguistán      | KG |
| Laos            | LA |
| Letonia          | LV |
| Líbano         | LB |
| Lesoto         | LS |
| Liberia         | LR |
| Libia           | LY |
| Liechtenstein   | LI |
| Lituania       | LT |
| Luxemburgo      | LU |
| RAE de Macao       | MO |
| Madagascar      | MG |
| Malaui          | MW |
| Malasia        | MY |
| Maldivas        | MV |
| Mali            | ML |
| Malta           | MT |
| Islas Marshall | MH |
| Martinica      | MQ |
| Mauritania      | SR |
| Mauricio       | MU |
| Mayotte         | YT |
| México          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Mónaco          | MC |
| Mongolia        | MN |
| Montenegro      | YO |
| Montserrat      | SRA |
| Marruecos         | MA |
| Mozambique      | MZ |
| Myanmar         | MM |
| Namibia         | NA |
| Nauru           | NR |
| Nepal           | NP |
| Países Bajos     | NL |
| Nueva Caledonia   | NC |
| Nueva Zelanda     | NZ |
| Nicaragua       | NI |
| Níger           | NE |
| Nigeria         | NG |
| Niue            | NU |
| Isla Norfolk  | NF |
| Corea del Norte     | KP |
| Macedonia del Norte | MK |
| Islas Marianas del Norte | NP |
| Noruega          | NO |
| Omán            | OM |
| Pakistán        | PK |
| Palaos           | PW |
| Autoridad Nacional Palestina | PS |
| Panamá          | PA |
| Papúa Nueva Guinea | PG |
| Paraguay        | PY |
| Perú            | PE |
| Filipinas     | PH |
| Islas Pitcairn | PN |
| Polonia          | PL |
| Portugal        | PT |
| Puerto Rico     | PR |
| Catar           | QA |
| Reunión         | RE |
| Rumania         | RO |
| Rusia          | RU |
| Ruanda          | RW |
| Saba            | XS |
| San Bartolomé | BL |
| San Cristóbal y Nieves | KN |
| Santa Lucía     | LC |
| San Martín    | MF |
| San Pedro y Miquelón | P.M. |
| San Vicente y las Granadinas | VC |
| Samoa           | WS |
| San Marino      | SM |
| Santo Tomé y Príncipe | ST |
| Arabia Saudí    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | SC |
| Sierra Leona    | SL | 
| Singapur       | SG |
| San Eustaquio  | XE |
| Sint Maarten    | SX |
| Eslovaquia        | SK |
| Eslovenia        | SL |
| Islas Salomón | SB |
| Somalia         | Así que |
| Sudáfrica    | ZA |
| Georgia del Sur e Islas Sandwich del Sur | GS |
| Sudán del Sur     | SS |
| España           | ES |
| Sri Lanka       | LK |
| Santa Elena, Ascensión y Tristán de Cunha | SH |
| Sudán           | SD |
| Surinam        | SR |
| Svalbard        | SJ |
| Suecia          | SE |
| Suiza     | CH |
| Siria           | SY |
| Taiwán          | TW |
| Tayikistán      | TJ |
| Tanzania        | TZ |
| Tailandia        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | PARA |
| Trinidad y Tobago | TT |
| Túnez         | TN |
| Turquía          | TR |
| Turkmenistán    | TM |
| Islas Turcas y Caicos | TC |
| Tuvalu          | TV |
| Islas Afueras de LOS EE. UU. | MENSAJERÍA UNIFICADA |
| Islas Vírgenes de los Estados Unidos | VI |
| Uganda          | UG |
| Ucrania         | UA |
| Emiratos Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | NOS |
| Uruguay         | UY |
| Uzbekistán      | UZ |
| Vanuatu         | VU |
| Ciudad del Vaticano    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis y Futuna | WF |
| Yemen           | VOSOTROS |
| Zambia          | ZM |
| Zimbabue        | ZW |

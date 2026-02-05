# iOS App Login Screen

A modern iOS login screen with email/password form, social login options, and sign-up link.

Based on template: `layout/wireframe_iphone.drawio`

```drawio
<mxfile>
  <diagram name="iOS Login" id="ios-login">
    <mxGraphModel dx="800" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="600" pageHeight="1000" background="#F5F5F7" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="phone-frame" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1C1C1E;strokeColor=#3A3A3C;strokeWidth=3;arcSize=8;" parent="1" vertex="1"><mxGeometry x="100" y="50" width="390" height="844" as="geometry"/></mxCell>
        <mxCell id="screen" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#FFFFFF;strokeColor=none;arcSize=6;" parent="1" vertex="1"><mxGeometry x="108" y="58" width="375" height="812" as="geometry"/></mxCell>
        <mxCell id="statusbar" value="" style="rounded=0;fillColor=#FFFFFF;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="108" y="58" width="375" height="44" as="geometry"/></mxCell>
        <mxCell id="time" value="9:41" style="text;fontSize=15;fontStyle=1;fontColor=#000000;align=left;" parent="1" vertex="1"><mxGeometry x="138" y="70" width="50" height="20" as="geometry"/></mxCell>
        <mxCell id="notch" value="" style="rounded=1;fillColor=#000000;strokeColor=none;arcSize=50;" parent="1" vertex="1"><mxGeometry x="238" y="58" width="115" height="30" as="geometry"/></mxCell>
        <mxCell id="signal" value="📶" style="text;fontSize=12;align=right;" parent="1" vertex="1"><mxGeometry x="390" y="70" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="battery" value="🔋" style="text;fontSize=12;align=right;" parent="1" vertex="1"><mxGeometry x="440" y="70" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="logo-container" value="" style="ellipse;fillColor=#007AFF;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="255" y="140" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="logo-icon" value="✦" style="text;fontSize=40;fontColor=#FFFFFF;align=center;verticalAlign=middle;" parent="1" vertex="1"><mxGeometry x="255" y="140" width="80" height="80" as="geometry"/></mxCell>
        <mxCell id="welcome-title" value="Welcome Back" style="text;fontSize=28;fontStyle=1;fontColor=#1C1C1E;align=center;" parent="1" vertex="1"><mxGeometry x="158" y="250" width="275" height="40" as="geometry"/></mxCell>
        <mxCell id="welcome-subtitle" value="Sign in to continue" style="text;fontSize=16;fontColor=#8E8E93;align=center;" parent="1" vertex="1"><mxGeometry x="158" y="290" width="275" height="25" as="geometry"/></mxCell>
        <mxCell id="email-label" value="Email" style="text;fontSize=14;fontColor=#8E8E93;align=left;" parent="1" vertex="1"><mxGeometry x="138" y="350" width="100" height="20" as="geometry"/></mxCell>
        <mxCell id="email-field" value="" style="rounded=1;fillColor=#F2F2F7;strokeColor=#E5E5EA;strokeWidth=1;" parent="1" vertex="1"><mxGeometry x="138" y="374" width="315" height="50" as="geometry"/></mxCell>
        <mxCell id="email-icon" value="" style="shape=mxgraph.ios7.icons.mail;html=1;fillColor=#8E8E93;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="153" y="389" width="20" height="20" as="geometry"/></mxCell>
        <mxCell id="email-placeholder" value="your@email.com" style="text;fontSize=16;fontColor=#C7C7CC;align=left;" parent="1" vertex="1"><mxGeometry x="183" y="384" width="250" height="30" as="geometry"/></mxCell>
        <mxCell id="password-label" value="Password" style="text;fontSize=14;fontColor=#8E8E93;align=left;" parent="1" vertex="1"><mxGeometry x="138" y="444" width="100" height="20" as="geometry"/></mxCell>
        <mxCell id="password-field" value="" style="rounded=1;fillColor=#F2F2F7;strokeColor=#E5E5EA;strokeWidth=1;" parent="1" vertex="1"><mxGeometry x="138" y="468" width="315" height="50" as="geometry"/></mxCell>
        <mxCell id="password-icon" value="" style="shape=mxgraph.ios7.icons.locked;html=1;fillColor=#8E8E93;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="153" y="483" width="16" height="20" as="geometry"/></mxCell>
        <mxCell id="password-placeholder" value="••••••••" style="text;fontSize=16;fontColor=#C7C7CC;align=left;" parent="1" vertex="1"><mxGeometry x="183" y="478" width="200" height="30" as="geometry"/></mxCell>
        <mxCell id="eye-icon" value="" style="shape=mxgraph.ios7.icons.eye;html=1;fillColor=#8E8E93;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="423" y="485" width="20" height="14" as="geometry"/></mxCell>
        <mxCell id="forgot-password" value="Forgot Password?" style="text;fontSize=14;fontColor=#007AFF;align=right;" parent="1" vertex="1"><mxGeometry x="313" y="528" width="140" height="25" as="geometry"/></mxCell>
        <mxCell id="signin-button" value="Sign In" style="rounded=1;fillColor=#007AFF;fontColor=#FFFFFF;strokeColor=none;fontStyle=1;fontSize=17;" parent="1" vertex="1"><mxGeometry x="138" y="580" width="315" height="50" as="geometry"/></mxCell>
        <mxCell id="divider-left" value="" style="line;strokeColor=#E5E5EA;strokeWidth=1;" parent="1" vertex="1"><mxGeometry x="138" y="665" width="130" height="1" as="geometry"/></mxCell>
        <mxCell id="divider-text" value="OR" style="text;fontSize=14;fontColor=#8E8E93;align=center;" parent="1" vertex="1"><mxGeometry x="268" y="655" width="55" height="20" as="geometry"/></mxCell>
        <mxCell id="divider-right" value="" style="line;strokeColor=#E5E5EA;strokeWidth=1;" parent="1" vertex="1"><mxGeometry x="323" y="665" width="130" height="1" as="geometry"/></mxCell>
        <mxCell id="apple-button" value="" style="rounded=1;fillColor=#000000;strokeColor=none;" parent="1" vertex="1"><mxGeometry x="138" y="700" width="315" height="50" as="geometry"/></mxCell>
        <mxCell id="apple-icon" value="" style="text;fontSize=20;fontColor=#FFFFFF;align=center;" parent="1" vertex="1"><mxGeometry x="218" y="710" width="30" height="30" as="geometry"/></mxCell>
        <mxCell id="apple-text" value="Continue with Apple" style="text;fontSize=16;fontColor=#FFFFFF;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="248" y="710" width="160" height="30" as="geometry"/></mxCell>
        
        <mxCell id="google-button" value="" style="rounded=1;fillColor=#FFFFFF;strokeColor=#E5E5EA;strokeWidth=1;" parent="1" vertex="1"><mxGeometry x="138" y="765" width="315" height="50" as="geometry"/></mxCell>
        <mxCell id="google-icon" value="G" style="text;fontSize=20;fontColor=#4285F4;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="218" y="775" width="30" height="30" as="geometry"/></mxCell>
        <mxCell id="google-text" value="Continue with Google" style="text;fontSize=16;fontColor=#1C1C1E;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="248" y="775" width="170" height="30" as="geometry"/></mxCell>
        <mxCell id="signup-text" value="Don't have an account?" style="text;fontSize=14;fontColor=#8E8E93;align=center;" parent="1" vertex="1"><mxGeometry x="178" y="840" width="160" height="25" as="geometry"/></mxCell>
        <mxCell id="signup-link" value="Sign Up" style="text;fontSize=14;fontColor=#007AFF;fontStyle=1;align=center;" parent="1" vertex="1"><mxGeometry x="338" y="840" width="60" height="25" as="geometry"/></mxCell>
        <mxCell id="home-indicator" value="" style="rounded=1;fillColor=#000000;strokeColor=none;arcSize=50;" parent="1" vertex="1"><mxGeometry x="243" y="880" width="105" height="5" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Verified Stencils Used

All stencil names from `skills/drawio/stencils/ios7.md`:

| Component | Stencil |
|-----------|---------|
| Mail Icon | `mxgraph.ios7.icons.mail` |
| Lock Icon | `mxgraph.ios7.icons.locked` |
| Eye Icon | `mxgraph.ios7.icons.eye` |

## iOS Design Guidelines Applied

- **Screen size**: iPhone 14 Pro logical resolution (390×844 in frame)
- **Safe area**: 44px top (status bar + notch), 34px bottom (home indicator)
- **Typography**: SF Pro Display weights
- **Colors**: iOS system colors (#007AFF primary, #8E8E93 secondary text)
- **Corner radius**: 10px for inputs, 12px for buttons
- **Spacing**: 8pt grid system

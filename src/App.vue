<template>
  <div v-for="(square, index) in squares" :key="index">
    <Punter v-if="punters.find(p => p.pos === index)" :punter="punters.find(p => p.pos === index)" />
    <Seat v-if="square" :occupied="square.occupied" :hairColour="square.hair"></Seat>
  </div>
</template>

<script>
import Seat from './components/Seat.vue'
import Punter from './components/Punter.vue'

export default {
  name: 'App',
  data() {
    return {
      squares: [
        0,0,0,"A32","A31","A30","A29","A28","A27","A26","A25","A24","A23","A22","A21","A20","A19","A18","A17",0,0,0,"A16","A15","A14","A13","A12","A11","A10","A9","A8","A7","A6","A5","A4","A3","A2","A1",0,0,0,
        0,0,0,"B32","B31","B30","B29","B28","B27","B26","B25","B24","B23","B22","B21","B20","B19","B18","B17",0,0,0,"B16","B15","B14","B13","B12","B11","B10","B9","B8","B7","B6","B5","B4","B3","B2","B1",0,0,0,
        0,0,0,"C32","C31","C30","C29","C28","C27","C26","C25","C24","C23","C22","C21","C20","C19","C18","C17",0,0,0,"C16","C15","C14","C13","C12","C11","C10","C9","C8","C7","C6","C5","C4","C3","C2","C1",0,0,0,
        0,0,0,"D32","D31","D30","D29","D28","D27","D26","D25","D24","D23","D22","D21","D20","D19","D18","D17",0,0,0,"D16","D15","D14","D13","D12","D11","D10","D9","D8","D7","D6","D5","D4","D3","D2","D1",0,0,0,
        0,0,0,"E32","E31","E30","E29","E28","E27","E26","E25","E24","E23","E22","E21","E20","E19","E18","E17",0,0,0,"E16","E15","E14","E13","E12","E11","E10","E9","E8","E7","E6","E5","E4","E3","E2","E1",0,0,0,
        0,0,0,"F32","F31","F30","F29","F28","F27","F26","F25","F24","F23","F22","F21","F20","F19","F18","F17",0,0,0,"F16","F15","F14","F13","F12","F11","F10","F9","F8","F7","F6","F5","F4","F3","F2","F1",0,0,0,
        0,0,0,"G32","G31","G30","G29","G28","G27","G26","G25","G24","G23","G22","G21","G20","G19","G18","G17",0,0,0,"G16","G15","G14","G13","G12","G11","G10","G9","G8","G7","G6","G5","G4","G3","G2","G1",0,0,0,
        0,0,0,"H32","H31","H30","H29","H28","H27","H26","H25","H24","H23","H22","H21","H20","H19","H18","H17",0,0,0,"H16","H15","H14","H13","H12","H11","H10","H9","H8","H7","H6","H5","H4","H3","H2","H1",0,0,0,
        0,0,0,"J32","J31","J30","J29","J28","J27","J26","J25","J24","J23","J22","J21","J20","J19","J18","J17",0,0,0,"J16","J15","J14","J13","J12","J11","J10","J9","J8","J7","J6","J5","J4","J3","J2","J1",0,0,0,
        0,0,0,"K32","K31","K30","K29","K28","K27","K26","K25","K24","K23","K22","K21","K20","K19","K18","K17",0,0,0,"K16","K15","K14","K13","K12","K11","K10","K9","K8","K7","K6","K5","K4","K3","K2","K1",0,0,0,
        ...Array.from(Array(82)).fill(0),
        0,0,0,0,0,0,0,0,0,0,0,"O25","O24","O23","O22","O21","O20","O19","O18","O17",0,"O16","O15","O14","O13","O12","O11","O10","O9","O8",0,0,"O7","O6","O5","O4","O3","O2","O1",0,0,
        0,0,0,0,0,0,0,0,0,0,0,"P25","P24","P23","P22","P21","P20","P19","P18","P17",0,"P16","P15","P14","P13","P12","P11","P10","P9","P8",0,0,"P7","P6","P5","P4","P3","P2","P1",0,0,
        0,0,0,0,0,0,0,0,0,0,0,"R25","R24","R23","R22","R21","R20","R19","R18","R17",0,"R16","R15","R14","R13","R12","R11","R10","R9","R8",0,0,"R7","R6","R5","R4","R3","R2","R1",0,0,
        0,0,"S32","S31","S30","S29","S28","S27","S26",0,0,"S25","S24","S23","S22","S21","S20","S19","S18","S17",0,"S16","S15","S14","S13","S12","S11","S10","S9","S8",0,0,"S7","S6","S5","S4","S3","S2","S1",0,0,
        0,0,"T32","T31","T30","T29","T28","T27","T26",0,0,"T25","T24","T23","T22","T21","T20","T19","T18","T17",0,"T16","T15","T14","T13","T12","T11","T10","T9","T8",0,0,"T7","T6","T5","T4","T3","T2","T1",0,0,
        0,0,"U32","U31","U30","U29","U28","U27","U26",0,0,"U25","U24","U23","U22","U21","U20","U19","U18","U17",0,"U16","U15","U14","U13","U12","U11","U10","U9","U8",0,0,"U7","U6","U5","U4","U3","U2","U1",0,0,
        0,0,"V32","V31","V30","V29","V28","V27","V26",0,0,"V25","V24","V23","V22","V21","V20","V19","V18","V17",0,"V16","V15","V14","V13","V12","V11","V10","V9","V8",0,0,"V7","V6","V5","V4","V3","V2","V1",0,0,
        0,0,"W32","W31","W30","W29","W28","W27","W26",0,0,"W25","W24","W23","W22","W21","W20","W19","W18","W17",0,"W16","W15","W14","W13","W12","W11","W10","W9","W8",0,0,"W7","W6","W5","W4","W3","W2","W1",0,0,
        0,0,"X32","X31","X30","X29","X28","X27","X26",0,0,"X25","X24","X23","X22","X21","X20","X19","X18","X17",0,"X16","X15","X14","X13","X12","X11","X10","X9","X8",0,0,"X7","X6","X5","X4","X3","X2","X1",0,0,
        0,0,"Y32","Y31","Y30","Y29","Y28","Y27","Y26",0,0,"Y25","Y24","Y23","Y22","Y21","Y20","Y19","Y18","Y17",0,"Y16","Y15","Y14","Y13","Y12","Y11","Y10","Y9","Y8",0,0,"Y7","Y6","Y5","Y4","Y3","Y2","Y1",0,0,
        0,0,"Z35","Z34","Z33","Z32","Z31","Z30","Z29",0,"Z28","Z27","Z26","Z25","Z24","Z23","Z22","Z21","Z20","Z19",0,"Z18","Z17","Z16","Z15","Z14","Z13","Z12","Z11","Z10","Z9",0,"Z8","Z7","Z6","Z5","Z4","Z3","Z2",0,0,
        0,"AA36","AA35","AA34","AA33","AA32","AA31","AA30","AA29",0,"AA28","AA27","AA26","AA25","AA24","AA23","AA22","AA21","AA20","AA19",0,"AA18","AA17","AA16","AA15","AA14","AA13","AA12","AA11","AA10","AA9",0,"AA8","AA7","AA6","AA5","AA4","AA3","AA2","AA1",0,
        0,"BB36","BB35","BB34","BB33","BB32","BB31","BB30","BB29",0,"BB28","BB27","BB26","BB25","BB24","BB23","BB22","BB21","BB20","BB19",0,"BB18","BB17","BB16","BB15","BB14","BB13","BB12","BB11","BB10","BB9",0,"BB8","BB7","BB6","BB5","BB4","BB3","BB2","BB1",0,
        0,"CC36","CC35","CC34","CC33","CC32","CC31","CC30","CC29",0,"CC28","CC27","CC26","CC25","CC24","CC23","CC22","CC21","CC20","CC19",0,"CC18","CC17","CC16","CC15","CC14","CC13","CC12","CC11","CC10","CC9",0,"CC8","CC7","CC6","CC5","CC4","CC3","CC2","CC1",0,
        0,"DD36","DD35","DD34","DD33","DD32","DD31","DD30","DD29",0,"DD28","DD27","DD26","DD25","DD24","DD23","DD22","DD21","DD20","DD19",0,"DD18","DD17","DD16","DD15","DD14","DD13","DD12","DD11","DD10","DD9",0,"DD8","DD7","DD6","DD5","DD4","DD3","DD2","DD1",0,
        0,0,"EE35","EE34","EE33","EE32","EE31","EE30","EE29",0,"EE28","EE27","EE26","EE25","EE24","EE23","EE22","EE21","EE20","EE19",0,"EE18","EE17","EE16","EE15","EE14","EE13","EE12","EE11","EE10","EE9",0,"EE8","EE7","EE6","EE5","EE4","EE3","EE2",0,0,
        0,0,"FF35","FF34","FF33","FF32","FF31","FF30","FF29",0,"FF28","FF27","FF26","FF25","FF24","FF23","FF22","FF21","FF20","FF19",0,"FF18","FF17","FF16","FF15","FF14","FF13","FF12","FF11","FF10","FF9",0,"FF8","FF7","FF6","FF5","FF4","FF3","FF2",0,0,
        0,0,"GG35","GG34","GG33","GG32","GG31","GG30","GG29",0,"GG28","GG27","GG26","GG25","GG24","GG23","GG22","GG21","GG20","GG19",0,"GG18","GG17","GG16","GG15","GG14","GG13","GG12","GG11","GG10","GG9",0,"GG8","GG7","GG6","GG5","GG4","GG3","GG2",0,0,
        0,0,"HH35","HH34","HH33","HH32","HH31","HH30","HH29",0,"HH28","HH27","HH26","HH25","HH24","HH23","HH22","HH21","HH20","HH19",0,"HH18","HH17","HH16","HH15","HH14","HH13","HH12","HH11","HH10","HH9",0,"HH8","HH7","HH6","HH5","HH4","HH3","HH2",0,0,
        0,0,"JJ35","JJ34","JJ33","JJ32","JJ31","JJ30","JJ29",0,"JJ28","JJ27","JJ26","JJ25","JJ24","JJ23","JJ22","JJ21","JJ20","JJ19",0,"JJ18","JJ17","JJ16","JJ15","JJ14","JJ13","JJ12","JJ11","JJ10","JJ9",0,"JJ8","JJ7","JJ6","JJ5","JJ4","JJ3","JJ2",0,0,
        0,0,"KK33","KK32","KK31","KK30","KK29","KK28","KK27",0,0,"KK26","KK25","KK24","KK23","KK22","KK21","KK20","KK19","KK18",0,"KK17","KK16","KK15","KK14","KK13","KK12","KK11","KK10","KK9",0,0,"KK8","KK7","KK6","KK5","KK4","KK3","KK2",0,0,
      ],
      emptySeats: [],
      punters: [],
      hairColours: ["#222", "#800000", "#cc6600", "#993300", "#ff6600", "#ffcc00", "#999", "#663300"]
    }
  },
  mounted() {
    this.emptySeats = this.getEmptySeats();
    this.squares = this.squares.map(s => s === 0 ? s : { seat: s, occupied: !this.emptySeats.includes(s), hair: this.emptySeats.includes(s) ? null : this.getHairColour() });
    const emptySquares = this.squares.map((s, i) => [i, s]).filter(a => a[1] === 0);
    this.punters = this.emptySeats.map(seat => {
      return { seat, pos: emptySquares[Math.random() * emptySquares.length | 0][0], dir: 'up', hair: this.getHairColour(), body: this.getBodyColour() };
    });
    setInterval(() => {
      this.punters = this.punters.map(p => this.movePunter(p));
    }, 1000);
  },
  methods: {
    getEmptySeats() {
      const seats = this.squares.filter(s => s);
      const empty = [];
      const getSeat = () => seats[Math.random() * seats.length | 0];
      for (let i = 0; i < 10; i++) {
        const newSeat = getSeat();
        empty.push(empty.includes(newSeat) ? getSeat() : newSeat);
      }
      return empty;
    },
    getHairColour() {
      return this.hairColours[Math.random() * this.hairColours.length | 0];
    },
    getBodyColour() {
      return `hsl(${Math.random() * 360 | 0}, 80%, 40%)`;
    },
    movePunter(p) {
      const newPunter = p;
      const { pos, dir } = p;
      const moves = { 'up': -41, 'down': 41, 'left': -1, 'right': 1 };
      if (this.squares[pos + moves[dir]] === 0) {
        newPunter.pos = pos + moves[dir];
      } else {
        const options = Object.keys(moves).filter(k => this.squares[pos + moves[k]] === 0);
        newPunter.dir = options[Math.random() * options.length | 0];
        newPunter.pos = pos + moves[newPunter.dir];
      }
      return newPunter;
    }
  },
  components: {
    Seat,
    Punter
  }
}
</script>

<style>
body {
  padding: 0;
  background-color: #ffffcc;
  display: flex;
  justify-content: center;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: grid;
  margin: 40px 0;
  grid-template-columns: repeat(41, 24px);
  grid-template-rows: repeat(20, 24px);
  grid-gap: 4px;
}
</style>

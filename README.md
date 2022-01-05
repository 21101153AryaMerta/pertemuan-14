# pertemuan-14

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/bootstrap.css">
    <style>
        .kotak{height: 300px;margin: 10px;}
    </style>
    <title>per 14</title>
</head>
<body>
    <div class="container">
        <h3>jQuery Show Hide Effect</h3>
        <button id="Tpilih1" type="button" class="btn btn-primary">pilih 1</button>
        <button id="Tpilih2" type="button" class="btn btn-primary">pilih 2</button>
        <select id="Spilih" class="btn btn-warning">
            <option>pilihan</option>
            <option value="A">pilih 1</option>
            <option value="B">pilih 2</option>
        </select>
    </div>

    <div class="container">
        <div class="pilih1">
            <div class="card">
                <div class="card-content kotak">
                    <h3>hitung keliling dan luas persegi panjang</h3>
                    <form class="row">
                        <label for="pj">nilai panjang</label>
                        <input type="number" id="PJ" class="form-contorl">
                        <label for="lb">nilai lebar</label>
                        <input type="number" id="LB" class="form-contorl">
                        <label for="luas">luas</label>
                        <input type="number" id="LUAS" class="form-contorl" disabled>
                        <label for="kll">keliling</label>
                        <input type="number" id="KLL" class="form-contorl" disabled>
                        <br>
                        <button type="button" id="HPP" class="btn btn-warning mt-3">hitung luas </button>
                    </form>

                </div>
            </div>
        </div>
        <div class="pilih2">
            <div class="card">
                <div class="card-content kotak">
                    isi dari pilih 2
                </div>
            </div>
        </div>
    </div>
</body>
<script src="js/bootstrap.js"></script>
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript">
    $(document).ready(function(){
        $(".pilih1").hide();
        $(".pilih2").hide();

        $("#Tpilih1").click(function(){
            $(".pilih1").show(1000);
            $(".pilih2").hide(500);
        });

        $("#Tpilih2").click(function(){
            $(".pilih2").show(1000);
            $(".pilih1").hide(500);
        });

        $("#Spilih").change(function(){
            var npilih = $("#Spilih").val();
            switch (npilih) {
                case "A":
                $(".pilih1").show(1000);
                $(".pilih2").hide(500);
                    break;
                case "B":
                $(".pilih2").show(1000);
                $(".pilih1").hide(500);
                    break;
                default:
                $(".pilih1").hide(500);
                $(".pilih2").hide(500);
                    break;
            }
        });

        $("#HPP").click(function(){
            var pj = $("#PJ").val();
            var lb = $("#LB").val();
            var luas = pj*lb;
            $("#LUAS").val(luas);
            var kell = 2*(parseFloat(pj)+ parseFloat(lb));
            $("#KLL").val(kell);
        });
    });
</script>
</html> 

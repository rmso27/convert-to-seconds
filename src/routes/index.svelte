<script>
    
    // Function to convert a time entry to seconds
    function timeConverter() {
        
        // Read user input
        var userInput = document.getElementById("input").value
        var unit = document.getElementById("unit").value
        var result = 0

        // Convert entry to seconds if entry is valid
        if (isNaN(userInput)) {
            document.getElementById("error").innerHTML = "Please insert a valid number"
        } else {
            if (unit == "week") {
                // 1 week = 604800 s
                var weekSecs = 604800
                result = userInput * weekSecs
            } else if (unit == "day") {
                // 1 day = 86400 s
                var daySecs = 86400
                result = userInput * daySecs
            } else if (unit == "hour") {
                // 1 hour = 3600 s
                var hourSecs = 3600
                result = userInput * hourSecs
            } else {
                // 1 minute = 60 s
                var minSecs = 60
                result = userInput * minSecs
            }
        }

        // Output result
        document.getElementById("result").value = result

    }

</script>

<div class = "main-title">
    <h1>Convert to Seconds</h1>
    <p>Convert a valid time entry to seconds</p>
</div>
<div class = "time-converter">
    <div class = "time-converter-initial">
        Initial value:
        <input type = "text" id = "input" name = "input">
        <select id = "unit">
            <option value = "week">Week(s)</option>
            <option value = "day">Day(s)</option>
            <option value = "hour">Hour(s)</option>
            <option value = "minute">Minute(s)</option>
        </select>
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <button on:click = {timeConverter}>Convert</button><br />
        <label id = "error"></label>
    </div>
    <div class = "time-converter-result">
        Result:
        <input type = "text" id = "result" readonly> seconds
    </div>
</div>
Using `1-counter.md` or `2-counter.md` from the easy section, can you create a
clock that shows you the current machine time?

Can you make it so that it updates every second, and shows time in the following formats - 

 - HH:MM::SS (Eg. 13:45:23)

 - HH:MM::SS AM/PM (Eg 01:45:23 PM)

const updateClock = () => {
    const now = new Date();

    // 24 hour clock
    const hours = (now.getHours()).toString().padStart(2, '0');
    const minutes = (now.getMinutes()).toString().padStart(2, '0');
    const seconds = (now.getSeconds()).toString().padStart(2, '0');

    // 12 hour clock
    const hour12 = ((hours) % 12).toString().padStart(2, '0');
    const ampm = hours > 12 ? 'PM' : 'AM';
    
    console.log(`24 hour format: ${hours}:${minutes}:${seconds}`);
    console.log(`12 hour format: ${hour12}:${minutes}:${seconds} ${ampm}`)
}

setInterval(updateClock, 1000);
updateClock();

  <template>
  <div>
    <div class="grid grid-cols-2 container mx-auto p-5 font-thin">
        <div class="flex items-center space-x-3">
            <div class="text-3xl font-bold text-white">PlanetCast</div>
            <div class="text-lg font-bold text-white flex">
                <div
                    class="mx-5 text-gray-300 hover:text-white hover:unerline select-none cursor-pointer"
                >Videos</div>
                <div
                    class="mx-5 text-gray-300 hover:text-white hover:unerline select-none cursor-pointer"
                >Staff</div>
                <div
                    class="mx-5 text-gray-300 hover:text-white hover:unerline select-none cursor-pointer"
                >Other</div>
            </div>
        </div>
        <div class="flex items-end justify-end space-x-3">
            <div class="text-lg font-bold text-white flex">
                <div
                    class="mx-5 text-gray-300 hover:text-white hover:unerline select-none cursor-pointer"
                >Log In</div>
            </div>
        </div>
    </div>
    <Nuxt></Nuxt>
</div>
</template>




    <style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@300&display=swap');

body {
  background-size: fit;
  background-position: center;
  background-image: url(/bg.webp);
  font-family: 'Noto Sans JP', sans-serif;
  box-sizing: border-box;
  display: block;
  font-size: 16px;
  line-height: 24px;
  text-size-adjust: 100%;
}

.font-bold {
  font-weight: 400;
}

</style>
<template>
	<div class="menu-item">
		<img class="menu-item__image" :src="image.source" :alt="image.alt" />
		<div>
			<h3>{{ name }}</h3>
			<p v-if="inStock">En stock</p>
			<p v-else>En rupture de stock</p>
			<div>
				<label for="add-item-quantity">Quantité : {{ quantity }}</label>
				<input v-model.number="localQuantity" id="add-item-quantity" type="number" />
				<button @click="addToShoppingCart(localQuantity)">
					Ajouter au panier
				</button>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "MenuItem",
	props: ["addToShoppingCart", "image", "inStock", "name", "quantity"],
	data() {
		return {
			localQuantity: this.quantity // Copie de la prop quantity dans une variable locale
		};
	}
};
</script>

<style></style>
